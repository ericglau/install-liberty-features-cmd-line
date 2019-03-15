# Installing Liberty features from command line

Setup:
1. Clone this repo or download `pom.xml` to any directory.

Installing features using feature names:
1. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` and `-Dliberty.feature` with your existing Liberty directory and the feature you want to install, respectively.
```
mvn net.wasdev.wlp.maven.plugins:liberty-maven-plugin:install-feature -Dliberty.directory=/opt/wlp -Dliberty.feature=jaxrs-2.1
```

Installing features using dependencies:
1. Modify the pom.xml to add dependencies, e.g.:
Open Liberty:
```
    <dependencies>
        <dependency>
            <groupId>io.openliberty.features</groupId>
            <artifactId>servlet-4.0</artifactId>
            <version>19.0.0.2</version>
            <type>esa</type>
            <scope>provided</scope>
        </dependency>   
    </dependencies>
```
WebSphere Liberty:
``` 
    <dependencies>
       <dependency>
           <groupId>com.ibm.websphere.appserver.features</groupId>
           <artifactId>servlet-3.0</artifactId>
           <version>19.0.0.2</version>
           <type>esa</type>
           <scope>provided</scope>
       </dependency>
    </dependencies>
```
2. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` with your existing Liberty directory.
