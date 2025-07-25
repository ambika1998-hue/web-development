pipeline {
    agent any  
    tools (
        jdk 'java-11'
        maven 'maven'
    )
    

    stages{
        stage ('git checkout'){
            steps {
                git branch :'main' , url:'https://github.com/ambika1998-hue/web-development.git'

            }
        }
        stage ('compile'){
            steps {
                sh 'mvn compile'
            }
        }
        stages('package'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage ('docker build'){
            steps{
                docker build -t ambika1998-hue/app .

            }
        }
        stage ('containerzation'){
            steps{
                docker run -it -d --name c1 -p 9000:80 ambika1998-hue/app
            }
            
        }
    }
}
