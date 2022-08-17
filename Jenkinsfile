pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '2124a685-8fbf-4a70-bf31-c7f2145c8a03', path: '',
                url: 'http://ec2-35-172-183-188.compute-1.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/*.war'
            }
        }
    }
}
