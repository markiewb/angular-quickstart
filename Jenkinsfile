pipeline {
    agent any
    
    stages {
        stage ("NPM build") {
            agent {
                docker {
                    image "teracy/angular-cli"
                    // to use current directory
                    reuseNode true
                } 
            }
            steps {
                echo "HELLOOOO"
                sh "npm --version"
                // download dependencies
                sh "npm install"
                //assemble
                sh "ng build"
            }
        }
        stage ("NPM test") {
            agent {
                docker {
                    image "teracy/angular-cli"
                    // to use current directory
                    reuseNode true
                } 
            }
            steps {
                sh "ng test"
            }
        }
    }
    post {
      always {
        archiveArtifacts artifacts: 'dist/**'
      } 
    }
}
