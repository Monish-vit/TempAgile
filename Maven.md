Maven



mvn --version 

in Jenkins -> tools -> maven installation 

M3 and auto 



create new repo 



**pom.xml** 



<project xmlns="http://maven.apache.org/POM/4.0.0"

xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation="http://maven.apache.org/POM/4.0.0

http://maven.apache.org/xsd/maven-4.0.0.xsd">

<modelVersion>4.0.0</modelVersion>

<groupId>com.example</groupId>

<artifactId>simple-maven-app</artifactId>

<version>1.0-SNAPSHOT</version>



<dependencies>

<dependency>

&#x09;<groupId>junit</groupId>

&#x09;<artifactId>junit</artifactId>

&#x09;<version>4.13.2</version>

&#x09;<scope>test</scope>

</dependency>

</dependencies>

</project>





src/main/java/com/example/App.java

src/test/java/com/example/AppTest.java







code for **App.java** for addition

package com.example;

public class App{

&#x09;public int add(int a, int b){

&#x09;	return a+b;

&#x09;}

}





**AppTest.java**

package com.example;

import org.junit.Test;

import static org.junit.Assert.\*;

public class AppTest{

&#x09;@Test

&#x09;public void testAdd(){

&#x09;	App app = new App();

&#x09;	assertEquals(5,app.add(2,3));

&#x09;}

}







clone repo to vs code



mvn clean test

or mvn compile 
mvn test
mvn clean install 










open Jenkins -> new -> pipeline



**Pipeline script**



pipeline{

&#x09;agent any

&#x09;tools{

&#x09;	maven 'M3'

&#x09;}

&#x09;stages{

&#x09;	stage('Checkout Git'){

&#x09;		steps{

&#x09;			git branch: 'main',

&#x09;			url: 'repo link'

&#x09;		}

&#x09;	}

&#x09;	stage('Build and Test'){

&#x09;		steps{

&#x09;			bat 'mvn clean test'

&#x09;		}

&#x09;	}

&#x09;}

}

























