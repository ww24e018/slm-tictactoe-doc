## mvn command

Neither `man mvn` or `mvn help` worked, so I started looking for usage-examples starting with the [moodle-link]()

```
mvn -v```
.. prints version information, confirming installation for example ([src](https://maven.apache.org/run.html))

```bash
mvn -h
mvn --help
```
.. prints usage information for the command. This is not super helpful,  many say "not supported anymore".

The src link for this (https://maven.apache.org/run.html) has more examples for usage.
For example: 
```
mvn checkstyle:check
```

## Applied to the the application with the lecture xml fragments 

In the "initial commit" state of our repo its possible to run this in the terminal. output implies violations of (assumed) default rules for checkstyle, e.g.
```
..
[ERROR] src/main/java/at/technikum/Main.java:[1] (javadoc) JavadocPackage: Missing package-info.java file.
[ERROR] src/main/java/at/technikum/Main.java:[3,1] (design) HideUtilityClassConstructor: Utility classes should not have a public or default constructor.
..
```

The Moodle contains a link to a *checkstyle.xml* listed after a pom-xml build config with the comment "Use this in your project". Its content is as follows (formatted for readability):
```xml
<module name="Checker">
  <property name="fileExtensions" value="java"/>
  <!-- Check for appropriate line length -->
  <module name="LineLength">
    <property name="max" value="100"/>
  </module>
  <module name="TreeWalker">
  <!-- Check for appropriate method length -->
    <module name="MethodLength">
      <property name="max" value="30"/>
    </module>
    <!-- Check for proper indentation and braces placement -->
    <module name="Indentation"/>
    <module name="LeftCurly"/>
    <module name="RightCurly"/>
    <!-- Check for appropriate naming conventions -->
    <module name="ConstantName"/>
    <module name="IllegalIdentifierName"/>
    <module name="LocalVariableName"/>
    <module name="MemberName"/>
    <module name="MethodName"/>
    <module name="PackageName"/>
    <module name="ParameterName"/>
    <module name="StaticVariableName"/>
    <module name="TypeName"/>
    <!-- Check for unused imports and variables -->
    <module name="UnusedImports"/>
    <module name="UnusedLocalVariable"/>
  </module>
</module>
```

Note: Copying from the browser window worked better for my than copying from the md-file. YMMV.

Just putting the file in the repo does not do anything yet, though (the output of `mvn checkstyle:check`remains unchanged.)

# merging lecture pom.xml fragment into pom.xml

The lecture-moodle provides a xml fragment: 
```xml
<build>  
    <plugins>  
        <plugin>  
            <groupId>org.apache.maven.plugins</groupId>  
            <artifactId>maven-surefire-plugin</artifactId>  
            <version>${check.latest.version}</version>  
        </plugin>  
        <plugin>  
            <groupId>org.apache.maven.plugins</groupId>  
            <artifactId>maven-checkstyle-plugin</artifactId>  
            <version>${check.latest.version}</version>  
            <configuration>  
                <configLocation>checkstyle.xml</configLocation>  
            </configuration>  
            <executions>  
                <execution>  
                    <goals>  
                        <goal>check</goal>  
                    </goals>  
                </execution>  
            </executions>  
        </plugin>  
    </plugins>  
</build>
```

A first try putting it at the end of the xml failed (in hindsight obvious, because of the "only one root-node" rule).
Putting it therefore at the end of the root node was tried. It resulted in a better error message, 
saying that `${check.latest.version}`is not allowed syntax here.

Hovering over the red text in intelliJ provides a possible string to replace it with
![[Pasted image 20260203133224.png]]
Sadly this is not a value that seems to be insertable but the version of the XML-spec?

The lecture Moodle provides 2 links to specific maven plugins:
https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-checkstyle-plugin
https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-surefire-plugin

This gives (currently) "3.5.4" for surefire and "3.6.0" for checkstyle. 
After that (and an exising.check) `mvn checkstyle:check` gives a different error.

> `unable to parse configuration stream - Document root element "module", must match DOCTYPE root "null".:1:24`

Naive web-searches point to "perhaps a doctype description is missing" as a possible source of this error. A search was made for an example checkstyle.xml, in the hope of compliant xml-syntax.

https://mvnrepository.com/artifact/org.apache.maven.plugins
into
https://maven.apache.org/plugins/
into
https://maven.apache.org/plugins/maven-checkstyle-plugin/
into
https://checkstyle.org
into
https://checkstyle.org/config.html

At which point the lack of doctypes became worrying, as all examples omited it.
Despair led to a websearch for "doctype for checkstyle.xml".
First result was this [link](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml) into the checkstyle github rep from which a doctype-to-copy could be obtained:
```xml
<?xml version="1.0"?>
<!DOCTYPE module PUBLIC
          "-//Checkstyle//DTD Checkstyle Configuration 1.3//EN"
          "https://checkstyle.org/dtds/configuration_1_3.dtd">
```
Copying that on the top of the checkstyle.xml resulted in `mvn checkstyle:check` running cleanly:
![[Pasted image 20260203140214.png]]

