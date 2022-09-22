# sonarqube-docker-compose-with-plugin-example
This repository is an example of how to use a sonarqube plugin in a docker compose environment

The plugin used is a fork of 
[SonarSource/sonar-custom-plugin-example](https://github.com/SonarSource/sonar-custom-plugin-example)
### build frontend
Execute in the plugin directory:
```
npm i
```

### build backend
Execute in the plugin directory:
```
mvn clean package
```

### build & start sonarqube
Execute in the repository root directory:
```
docker-compose up
```

### copy plugin .jar to extensions
After sonarqube is ready and the volumes have been created execute the following command to add the plugin to sonarqube
```
cp plugin/target/sonar-example-plugin-*.jar extensions/plugins/
```
Now restart the docker-compose and the plugin should be installed

To check this go to
[http://localhost:9000/admin/marketplace?filter=installed](http://localhost:9000/admin/marketplace?filter=installed)

You should also see a "More" tab.

### access sonarqube
Go to  [http://localhost:9000/](http://localhost:9000/)