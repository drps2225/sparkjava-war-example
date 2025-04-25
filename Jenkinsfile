pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH
    }
    stages {
       stages('Mybuild') {
           steps {
               sh 'mvn clean package'
           }
       }
    }
} 
