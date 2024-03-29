# Installing Liberty features from command line

## Setup
1. Have an existing Liberty directory.
1. Clone this repo or download `pom.xml` to any directory.

## Installing features using feature names
1. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` and `-Dliberty.feature` with your existing Liberty directory and the feature you want to install, respectively.
```
mvn net.wasdev.wlp.maven.plugins:liberty-maven-plugin:install-feature -Dliberty.directory=/opt/wlp -Dliberty.feature=jaxrs-2.1
```

## Installing features using dependencies
1. Modify the pom.xml to add dependencies, e.g.:
#### Open Liberty:
```
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>io.openliberty.features</groupId>
                <artifactId>features-bom</artifactId>
                <version>19.0.0.2</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

    <dependencies>
        <dependency>
            <groupId>io.openliberty.features</groupId>
            <artifactId>jaxrs-2.1</artifactId>
            <type>esa</type>
        </dependency>
    </dependencies>
```
#### WebSphere Liberty:
``` 
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.ibm.websphere.appserver.features</groupId>
                <artifactId>features-bom</artifactId>
                <version>19.0.0.2</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

    <dependencies>
       <dependency>
           <groupId>com.ibm.websphere.appserver.features</groupId>
           <artifactId>servlet-3.0</artifactId>
           <type>esa</type>
       </dependency>
    </dependencies>
```
2. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` with your existing Liberty directory.

## Installing user features
1. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` and `-Dliberty.feature` with your existing Liberty directory and the path to the user feature you want to install, respectively.
```
mvn net.wasdev.wlp.maven.plugins:liberty-maven-plugin:install-feature -Dliberty.directory=/opt/wlp -Dliberty.feature="/mydir/com.ibm.websphere.appserver.portlet-2.0.esa" -Dliberty.feature.acceptLicense=true
```
