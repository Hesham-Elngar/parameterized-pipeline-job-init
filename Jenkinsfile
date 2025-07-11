
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Test') {
      steps {
        bat 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }
    
    stage('Containerization') {
      steps {
        bat 'echo Docker Build Image..'
        bat 'echo Docker Tag Image....'
        bat 'echo Docker Push Image......'
      }
    }

    stage('Kubernetes Deployment') {
      steps {
        bat 'echo Deploy to Kubernetes using ArgoCD'
      }
    }
    
    stage('Integration Testing') {
      steps {
  
        bat 'echo Testing using cURL commands......'
      }
    }
  }
  tools {
    maven 'Maven_3.9.9'
  }

}
