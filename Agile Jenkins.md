Agile Jenkins

**#1**

new item - freestyle 

In build steps : execute as windows batch command

echo "hello Jenkins"

echo "Name"

date /t



save, build 



**#2** 

in manage jenking - git installation - Default and automatically



in source code mgmt - add git repo link 

build step : echo "change detected"

ls -l

poll scm \*\*\*\*\* 



**#3 job flow**

create 3 freestyle job

install stage view and observe stage wise execution

pipeline flow - up down layout and initial as build



in A - post build action - Job-B-Test,

trigger only if build is stable



in B - post build action - Job-C-Deploy

build A and see other also get triggered



**#4 pipeline** 

in manage Jenkins plugin install Pipeline: Stage View

new item - pipeline 

**script:**

pipeline{

&#x09;agent any

&#x09;stages{

&#x09;	stage('Build'){

&#x09;		steps{echo 'Building..'}

&#x09;	}

&#x09;	stage('Test'){

&#x09;		steps{echo 'Testing..'}

&#x09;	}

&#x09;	stage('Deploy'){

&#x09;		steps{echo 'Deploying..'}

&#x09;	}

&#x09;}

}







**# Jenkins pipeline**

create pipeline job

script



write in text file and save as Jenkinsfile , commit to github



pipeline {

&#x09;// 1. agent: Tells Jenkins where to run the job.

&#x09;// 'any' means run it on any available executor in your Docker container.

&#x09;agent any

&#x09;// 2. stages: The container for all the work we want to do.

&#x09;stages {

&#x09;// 3. stage: Defines a specific phase of the process (e.g., Build).

&#x09;	stage('Build') {

&#x09;	// 4. steps: The actual commands/actions inside a stage.

&#x09;		steps {

&#x09;			echo 'Compiling the source code...'

&#x09;		}

&#x09;	}

&#x09;	stage('Test') {

&#x09;		steps {

&#x09;			echo 'Executing JUnit tests...'

&#x09;			echo 'Test Coverage: 95%'

&#x09;		}

&#x09;	}

&#x09;	stage('Deploy'){

&#x09;		steps {

&#x09;			echo 'Pushing artifacts to the production server...'

&#x09;		}

&#x09;	}

&#x09;}

}



Commit that text file name as : Jenkinsfile

in cmd prompt

git init

git remote add origin url link

git pull origin main

git add Jenkinsfile

git commit -m "Add jenkinsfile"

//git push origin main

git branch -M main

git push origin main



in Jenkins 

pipeline script from scm

scm -> repo url add

branch : main

script path : Jenkinsfile

in poll scm \*\*\*\*\*



modify and rebuild - do change in Jenkinsfile (Add new stage)

git init

git remote add origin <repo url>

git add Jenkinsfile

git commit -m "modified jenkins"

git push origin main







