pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Sunilkumar15874/Finance-Project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with sunil'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with sunil'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with sunil'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with sunil'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t sk15874/addressbookupdate:1.0'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 sk15874/addressbookupdate:1.0'
            }
        }   
    }
}
