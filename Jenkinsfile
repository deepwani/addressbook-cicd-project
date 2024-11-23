pipeline{
    agent any
    stages{
        stage('GitHub Validation'){
          steps{
                 git url: 'https://github.com/akshu20791/addressbook-cicd-project'
          }
        }
        stage('compiling the code'){
          steps{
                 sh 'mvn compile'
          }
        }
        stage('Testing the Code'){
            steps{
                sh 'mvn test'
            }
        }
        stage('QA of the code'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage("deploy the project on tomcat"){
            steps{
                sh "sudo mv /var/lib/jenkins/workspace/mypipeline/target/addressbook.war /home/ubuntu/apache-tomcat-8.5.100/webapps/"
            }
        }
    }
}
