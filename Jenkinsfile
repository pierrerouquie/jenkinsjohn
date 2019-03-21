pipeline {
  agent any
  stages {
    stage('error') {
      agent {
        dockerfile {
          filename 'Dockerfile'
        }

      }
      steps {
        sh '''pipeline {
    agent {
        docker { image \'img-python\' }
    }
    stages {
        stage(\'Launch\') {
            steps {
                sh \'python /srv/test/test.py\'
            }
        }
        stage(\'Echo\') {
            steps {
                sh \'whoami\'
            }
        }
    }
}'''
        }
      }
    }
  }