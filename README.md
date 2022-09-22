# sonarqube-docker-compose-with-plugin-example
This Repository is an example of how to use a sonarqube plugin in a docker compose environment

### build frontend
execute in the plugin directory:
```
npm i
```

### build backend
execute in the plugin directory:
```
cd plugin && mvn clean package
```

### build & start sonarqube
execute in the repository root directory:
```
docker-compose up
```

### copy plugin .jar to extensions
after sonarqube is ready and the volumes have been created execute the following command to add the plugin to sonarqube
```
cp plugin/target/sonar-example-plugin-*.jar extensions/plugins/
```
now restart the docker-compose and the plugin should be installed

to check this go to
[http://localhost:9000/admin/marketplace?filter=installed](http://localhost:9000/admin/marketplace?filter=installed)

you should also see a "More" tab.

### access sonarqube
go to  [http://localhost:9000/](http://localhost:9000/)