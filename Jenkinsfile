pipeline {
  agent {
        label " master"
    }
    tools {
        maven 'M2'
        jdk 'JDK'
        nodejs 'NODEJS'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'cd NumberGenerator & mvn install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
      stage('Nodejs') {
      steps {
        bat 'npm -v'
        bat 'node -v'
      }
    }
        }
    
}
