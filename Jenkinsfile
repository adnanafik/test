pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'building'
          }
        }
        stage('Archiving') {
          steps {
            echo 'Archiving'
          }
        }
        stage('Post archiving') {
          steps {
            echo 'Post archiving'
          }
        }
      }
    }
    stage('Testing') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Dockerizing') {
      parallel {
        stage('Dockerizing') {
          steps {
            echo 'Dockerizing'
          }
        }
        stage('Post Docker') {
          steps {
            echo 'Post Docker'
          }
        }
      }
    }
    stage('Pushing to registry') {
      steps {
        echo 'Pushing to Registry'
      }
    }
    stage('Deploying on prod') {
      steps {
        input(message: 'Do you want to deploy to prod?', id: 'is_prod_deploy')
      }
    }
  }
}