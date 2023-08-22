pipeline{
    agent any
        tools{
            maven 'local-maven'
            }
    stages{
        stage('SCM Checkout'){
                             steps{
                               git branch: 'master-1', url: 'https://github.com/satya918/firstSpringBootApplication.git'
                                  }
                            } 
        stage('Build'){
                                steps{
                                    sh 'mvn clean package'
                                    }
                        } 
    stage ('Deploy to tomcat server'){
                        steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcatcreds', path: '', url: 'http://13.53.36.13:9092/')], contextPath: '/firstSpringBootApplication-0.0.1-SNAPSHOT', war: '**/*.war'
            }
        }
    }
    }
