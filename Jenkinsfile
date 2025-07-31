pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build & Complie') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }

       
        stage('Deploy to Tomcat Web Server') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatServer', path: '', url: 'http://3.135.185.224:8080/')], contextPath: 'webapp', war: '**/*.war'
        }
    }

}
