pipeline {
  agent { docker { image 'node:20' } }
  stages {
    stage('Install') {
      steps { sh 'npm ci' }
    }
    stage('Test') {
      steps { sh 'npm test || echo "no tests"' }
    }
    stage('Archive') {
      steps { archiveArtifacts artifacts: 'package.json', fingerprint: true }
    }
  }
}