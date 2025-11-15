pipeline {
  agent any

  environment {
    IMAGE = "portfolio-site"
    CONTAINER = "portfolio"
    HOST_PORT = "80"
  }

  stages {
    stage('Checkout') {
      steps {
        git url: 'https://github.com/<your-username>/portfolio', credentialsId: 'github-token'
      }
    }

    stage('Build') {
      steps {
        sh "docker build -t ${IMAGE}:${BUILD_NUMBER} ."
      }
    }

    stage('Deploy') {
      steps {
        sh """
          docker stop ${CONTAINER} || true
          docker rm ${CONTAINER} || true
          docker run -d --name ${CONTAINER} -p ${HOST_PORT}:80 ${IMAGE}:${BUILD_NUMBER}
        """
      }
    }

    stage('Smoke Test') {
      steps {
        sh """
          sleep 2
          if ! curl -s --fail http://localhost:${HOST_PORT} >/dev/null; then
            echo 'Deploy failed'
            exit 1
          fi
        """
      }
    }

    stage('Cleanup') {
      steps { sh "docker image prune -f" }
    }
  }
}

