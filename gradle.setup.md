# Gradle setup

```java
group 'com.adechinan600'
version '1.0-SNAPSHOT'

apply plugin: 'java'

sourceCompatibility = 1.8

repositories {
    mavenCentral()
}

// this task generate a jar final with all dependencies
task fatJar(type: Jar) {
    manifest {
        attributes 'Implementation-Title': 'Gradle Jar File Example',
                'Implementation-Version': version,
                'Main-Class': 'com.mkyong.DateUtils'
    }
    baseName = project.name + '-all'
    from { configurations.compile.collect { it.isDirectory() ? it : zipTree(it) } }
    with jar
}


dependencies {
    testCompile group: 'junit', name: 'junit', version: '4.12'
    /*create libs dir at same level as src folder and put in your external jars*/
    compile fileTree(include: ['*.jar'], dir: 'libs')

}

```