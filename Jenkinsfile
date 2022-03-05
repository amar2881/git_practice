pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Archive Artifact') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }

    stage('publish result') {
      steps {
        junit '**/*.xml'
      }
    }

  }
}