pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the test job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the second job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the pacakge job'
        sh 'npm run package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}