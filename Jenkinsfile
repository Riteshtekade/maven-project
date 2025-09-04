pipeline {
agent any
stages
{
    stage('scm checkout') {
      steps {git 'https://github.com/Riteshtekade/maven-project.git'}
    }

    stage('Validat the code'){
      steps {withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
          sh 'mvn validate' 
        }
      }
    }
    stage('Compile the code') {
      steps {withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
          sh 'mvn compile'
        }
      }
    }
    stage('Package the code') {
      steps {withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
          sh 'mvn package'
        }
      }
    }
  }
}