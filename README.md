# gradletuto
Un court tutoriel Gradle.

## Première tâche
```
$ gradle tasks
...
$ gradle Hello
:Hello
Hello !

BUILD SUCCESSFUL

Total time: 0.991 secs
```

### Voir aussi
* [Task](https://docs.gradle.org/current/dsl/org.gradle.api.Task.html)

## Dépendances entre tâches
```
$ gradle world
:hello
Hello, :world
world !

BUILD SUCCESSFUL

Total time: 0.989 secs
```

## Construit un projet groovy
```
$ gradle tasks
...
$ gradle build
:compileJava UP-TO-DATE
:compileGroovy
Download https://repo1.maven.org/maven2/org/codehaus/groovy/groovy-all/2.4.5/groovy-all-2.4.5.jar
:processResources UP-TO-DATE
:classes
:jar
:assemble
:compileTestJava UP-TO-DATE
:compileTestGroovy UP-TO-DATE
:processTestResources UP-TO-DATE
:testClasses UP-TO-DATE
:test UP-TO-DATE
:check UP-TO-DATE
:build

BUILD SUCCESSFUL

Total time: 1 mins 10.772 secs
$ ls build/libs
gradletuto.jar
$ java -cp $GROOVY_HOME/lib/groovy-2.4.5.jar:build/libs/gradletuto.jar fr.uvsq.doosa.gradletuto.Main
Hello
```

### Voir aussi
* Plugin [Groovy](https://docs.gradle.org/current/userguide/groovy_plugin.html)
* Plugin [Java](https://docs.gradle.org/current/userguide/java_plugin.html)
* [repositories](https://docs.gradle.org/current/dsl/org.gradle.api.Project.html#org.gradle.api.Project:repositories%28groovy.lang.Closure%29)
* [dependencies](https://docs.gradle.org/current/dsl/org.gradle.api.Project.html#org.gradle.api.Project:dependencies%28groovy.lang.Closure%29)

## Lancer l'application
```
$ gradle run
:compileJava UP-TO-DATE
:compileGroovy UP-TO-DATE
:processResources UP-TO-DATE
:classes UP-TO-DATE
:run
Hello

BUILD SUCCESSFUL

Total time: 1.663 secs
```

### Voir aussi
* Plugin [application](https://docs.gradle.org/current/userguide/application_plugin.html)
* [Passer des arguments pour l'application à gradle run](http://stackoverflow.com/questions/27604283/gradle-task-pass-arguments-to-java-application)

## Intégrer les tests unitaires
```
$ gradle build
:compileJava UP-TO-DATE
:compileGroovy
:processResources UP-TO-DATE
:classes
:jar
:startScripts
:distTar
:distZip
:assemble
:compileTestJava UP-TO-DATE
:compileTestGroovy
:processTestResources UP-TO-DATE
:testClasses
:test
:check
:build

BUILD SUCCESSFUL

Total time: 4.042 secs
```

### Voir aussi
* [Groovy Testing Guide](http://docs.groovy-lang.org/docs/latest/html/documentation/core-testing-guide.html)

## Créer un uberjar (jar avec les dépendances)
```
$ gradle tasks
...
Shadow tasks
------------
knows - Do you know who knows?
shadowJar - Create a combined JAR of project and runtime dependencies
...
$ gradle shadowJar
:compileJava UP-TO-DATE
:compileGroovy UP-TO-DATE
:processResources UP-TO-DATE
:classes UP-TO-DATE
:shadowJar

BUILD SUCCESSFUL

Total time: 3.441 secs
$ ls build/libs
gradletuto-all.jar  gradletuto.jar
$ java -jar build/libs/gradletuto-all.jar
Hello
```

### Voir aussi
* Plugin [Shadow](https://github.com/johnrengelman/shadow)
* [Writing Custom Plugins](https://docs.gradle.org/current/userguide/custom_plugins.html)
* [Gradle plugin portal](https://plugins.gradle.org/)

## Références
* [Gradle User Guide](https://docs.gradle.org/current/userguide/userguide.html)
* [Gradle Build Language Reference](https://docs.gradle.org/current/dsl/)
* [Building and Testing With Gradle!](http://www2.gradleware.com/l/68052/2015-01-13/6dm)
* [Gradle Beyond the Basics!](http://www2.gradle.com/l/68052/2015-01-26/23s5)
* [The Gradle build system- Tutorial ](http://www.vogella.com/tutorials/Gradle/article.html)
* [Gradle Tutorial](http://rominirani.com/2014/07/28/gradle-tutorial-part-1-installation-setup/)
* [Gradle Goodness](http://mrhaki.blogspot.fr/search/label/Gradle)
* [Getting Started With Gradle](http://www.petrikainulainen.net/getting-started-with-gradle/)
