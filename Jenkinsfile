pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Venumadhav09/healthcare-project'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with venu'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with venu'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with venu'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with venu'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg1 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8082:8082 --name c001 myimg1'
            }
        }   
    }
}
