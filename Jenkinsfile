pipeline {
  agent any
  tools {
    maven 'maven'
    }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
        }
      }

    stage ("Clone repo"){
      steps {
        sh "git clone https://github.com/Sawssen19/TP3-Jenkins.git"
        }
      }


    stage ("Generate backend image"){
      steps {
        dir("TP3-Jenkins"){
          sh "mvn clean install"
          sh "docker build -t doctp3jenk ."
          }
        }
      }

    stage ("Run docker compose"){
      steps {
        dir("TP3-Jenkins"){
          sh "docker-compose up -d"
          }
        }
      }
    }
  }
