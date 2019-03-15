# Installing Liberty features from command line

1. Clone this repo or download `pom.xml` to any directory.
2. From the directory with the `pom.xml`, run the following command, replacing the values of `-Dliberty.directory` and `-Dliberty.feature` with your existing Liberty directory and the feature you want to install, respectively.
```
mvn net.wasdev.wlp.maven.plugins:liberty-maven-plugin:install-feature -Dliberty.directory=/opt/wlp -Dliberty.feature=jaxrs-2.1
```
