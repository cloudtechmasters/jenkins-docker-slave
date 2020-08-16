pipeline{
    agent {
        docker { image 'cloudtechmasters/jenkins-slave:latest' }
    }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/cloudtechmasters/springboot-weekend-session.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
