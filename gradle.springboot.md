```java

buildscript {
	ext {
		springBootVersion = '1.5.2.RELEASE'
	}
	repositories {
		mavenCentral()
	}
	dependencies {
		classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
	}
}

apply plugin: 'java'
apply plugin: 'eclipse'
apply plugin: 'org.springframework.boot'

version = '0.0.1-SNAPSHOT'
sourceCompatibility = 1.8

repositories {
	mavenCentral()
}


dependencies {
	compile('org.springframework.boot:spring-boot-starter-actuator')
	compile('org.springframework.cloud:spring-cloud-starter-oauth2')
	compile('org.springframework.boot:spring-boot-starter-data-couchbase')
	compile('org.springframework.boot:spring-boot-starter-data-elasticsearch')
	compile('org.springframework.boot:spring-boot-starter-data-jpa')
	compile('org.springframework.boot:spring-boot-starter-data-ldap')
	compile('org.springframework.boot:spring-boot-starter-data-mongodb')
	compile('org.springframework.boot:spring-boot-starter-data-neo4j')
	compile('org.springframework.boot:spring-boot-starter-data-redis')
	compile('org.springframework.boot:spring-boot-starter-data-rest')
	compile('org.springframework.data:spring-data-rest-hal-browser')
	compile('org.springframework.data:spring-data-rest-hal-browser')
	compile('org.springframework.boot:spring-boot-starter-hateoas')
	compile('org.springframework.boot:spring-boot-starter-jersey')
	compile('org.springframework.kafka:spring-kafka')
	compile('org.springframework.boot:spring-boot-starter-mail')
	compile('io.ratpack:ratpack-spring-boot:1.1.1')
	compile('org.springframework.boot:spring-boot-starter-security')
	compile('org.springframework.boot:spring-boot-starter-social-facebook')
	compile('org.springframework.boot:spring-boot-starter-social-linkedin')
	compile('org.springframework.boot:spring-boot-starter-social-twitter')
	compile('com.stormpath.spring:stormpath-default-spring-boot-starter')
	compile('org.springframework.boot:spring-boot-starter-thymeleaf')
	compile('com.vaadin:vaadin-spring-boot-starter')
	compile('org.springframework.boot:spring-boot-starter-web')
	compile('org.springframework.boot:spring-boot-starter-websocket')
	runtime('org.springframework.boot:spring-boot-devtools')
	runtime('com.h2database:h2')
	runtime('mysql:mysql-connector-java')
	runtime('org.postgresql:postgresql')
	compileOnly('org.projectlombok:lombok')
	testCompile('org.springframework.boot:spring-boot-starter-test')
}

// add this only if u use stormpath, vaadin or cloud

dependencyManagement {
	imports {
		mavenBom "com.stormpath.sdk:stormpath-bom:1.5.2"
		mavenBom "com.vaadin:vaadin-bom:8.0.5"
		mavenBom "org.springframework.cloud:spring-cloud-dependencies:Dalston.RELEASE"
	}
}

```