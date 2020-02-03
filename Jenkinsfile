pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v $HOME/.m2:/root/.m2'
    }

  }
  stages {
    stage('PreTest') {
      steps {
        sh 'pwd && ls -lah'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean install -DskipTests -DskipITs && mvn jetty:run'
      }
    }

  }
}