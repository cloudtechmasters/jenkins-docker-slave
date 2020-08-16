pipeline{
    agent {
        docker { image 'cloudtechmasters/jenkins-slave:latest' }
    }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/Naresh240/HelloSpringEKS.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
