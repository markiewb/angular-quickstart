pipeline {
    agent any
    
    stages {
        stage ("NPM build") {
            agent {
                docker {
                    image "teracy/angular-cli"
                    //args "-v $(pwd):/opt -w /opt"
                    args '-u root'
                    //image "node:8-alpine"
                    //args "-v /dir:dir"
                } 
            }
            steps {
                echo "HELLOOOO"
                sh "npm --version"
                sh "ng build"
                //https://github.com/markiewb/angular-quickstart.git
            }
        }
    }
}
