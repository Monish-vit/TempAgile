Here’s a \*\*complete step-by-step guide + all required code\*\* to finish your lab assignment (Git + VS Code + Jenkins CI pipeline).



\---



\# 🧩 PART 1: Create Java Program



You can choose either option. I’ll give you \*\*Calculator.java (recommended)\*\*.



\---



\## ✅ `Calculator.java`



```java

import java.util.Scanner;



public class Calculator {

&#x20;   public static void main(String\[] args) {

&#x20;       Scanner sc = new Scanner(System.in);



&#x20;       System.out.println("Enter first number:");

&#x20;       double a = sc.nextDouble();



&#x20;       System.out.println("Enter second number:");

&#x20;       double b = sc.nextDouble();



&#x20;       System.out.println("Choose operation (+, -, \*, /):");

&#x20;       char op = sc.next().charAt(0);



&#x20;       double result;



&#x20;       switch(op) {

&#x20;           case '+':

&#x20;               result = a + b;

&#x20;               break;

&#x20;           case '-':

&#x20;               result = a - b;

&#x20;               break;

&#x20;           case '\*':

&#x20;               result = a \* b;

&#x20;               break;

&#x20;           case '/':

&#x20;               if(b != 0)

&#x20;                   result = a / b;

&#x20;               else {

&#x20;                   System.out.println("Cannot divide by zero");

&#x20;                   return;

&#x20;               }

&#x20;               break;

&#x20;           default:

&#x20;               System.out.println("Invalid operator");

&#x20;               return;

&#x20;       }



&#x20;       System.out.println("Result: " + result);

&#x20;   }

}

```



\---



\# 🧩 PART 2: Push Code to GitHub



\### Step 1: Initialize Git



```bash

git init

git add .

git commit -m "Initial commit with Calculator program"

```



\---



\### Step 2: Create repo on GitHub and connect



```bash

git remote add origin https://github.com/username/repo.git

git branch -M main

git push -u origin main

```



\---



\# 🧩 PART 3: Clone in VS Code



In VS Code terminal:



```bash

git clone https://github.com/username/repo.git

cd repo

```



\---



\# 🧩 PART 4: Create Jenkinsfile (IMPORTANT)



Create a file named:



```bash

Jenkinsfile

```



\---



\## ✅ Jenkinsfile (CI Pipeline) **Use bat**



```groovy

pipeline {

&#x20;   agent any



&#x20;   stages {



&#x20;       stage('Clone Repository') {

&#x20;           steps {

&#x20;               git 'https://github.com/username/repo.git'

&#x20;           }

&#x20;       }



&#x20;       stage('Compile') {

&#x20;           steps {

&#x20;               sh 'javac Calculator.java'

&#x20;           }

&#x20;       }



&#x20;       stage('Run Program') {

&#x20;           steps {

&#x20;               sh 'echo "5\\n3\\n+" | java Calculator'

&#x20;           }

&#x20;       }

&#x20;   }



&#x20;   post {

&#x20;       success {

&#x20;           archiveArtifacts artifacts: '\*.class', fingerprint: true

&#x20;       }

&#x20;       failure {

&#x20;           echo 'Build Failed!'

&#x20;       }

&#x20;   }

}

```



\---



\## 🔍 What this pipeline does:



\* Pulls code from GitHub

\* Compiles using `javac`

\* Runs program using `java`

\* Archives `.class` file if success

\* Stops if compilation fails ❌



\---



\# 🧩 PART 5: Push Jenkinsfile



```bash

git add Jenkinsfile

git commit -m "Added Jenkins pipeline"

git push origin main

```



\---



\# 🧩 PART 6: Setup Jenkins Job



\### Step-by-step:



1\. Open Jenkins Dashboard

2\. Click \*\*New Item\*\*

3\. Enter name → select \*\*Pipeline\*\*

4\. Click \*\*OK\*\*



\---



\### Configure:



\* Pipeline → \*\*Pipeline script from SCM\*\*

\* SCM → Git

\* Repo URL → your GitHub repo

\* Branch → `main`

\* Script Path → `Jenkinsfile`



Click \*\*Save\*\*



\---



\# 🧩 PART 7: Enable Auto Trigger (CI Requirement)



\### In Jenkins:



\* Go to job → Configure

\* Enable ✅ \*\*GitHub hook trigger for GITScm polling\*\*



\---



\### In GitHub:



\* Go to repo → Settings → Webhooks

\* Add webhook:



```bash

http://<your-jenkins-url>/github-webhook/

```



\* Content type → `application/json`



\---



\# 🧩 PART 8: Test Pipeline



\### Trigger build:



\* Click \*\*Build Now\*\* OR

\* Push new change:



```bash

git commit -am "test change"

git push

```



\---



\# 🧩 PART 9: Verify Requirements ✅



✔ Auto trigger on push

✔ Code pulled from Git

✔ Compiled using `javac`

✔ Executed using `java`

✔ Fail if compile error

✔ `.class` archived



\---



\# 📊 Where to check output



\* Console Output → shows compile + run logs

\* Build → Artifacts → `.class` file



\---



\# 🧠 Simple Flow



```

GitHub → Jenkins → Build → Compile → Run → Archive

```



\---



\# ⚠️ Common Errors (IMPORTANT)



\* ❌ `javac not found` → Install JDK \& set PATH

\* ❌ GitHub webhook not working → check URL

\* ❌ Permission denied → use proper credentials



\---



\# 🎯 Final Outcome



You successfully implemented:



\* ✅ Git-based project

\* ✅ CI pipeline in Jenkins

\* ✅ Automation on code push

\* ✅ Artifact storage



\---



If you want, I can also give:



\* ⭐ Student grading program version

\* 🔥 Viva questions + answers for this lab

\* 🛠️ Troubleshooting guide (very useful before submission)



