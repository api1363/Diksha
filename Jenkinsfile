pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
               bat "rmdir  /s /q Diksha"
                bat "git clone https://github.com/api1363/Diksha.git"
                bat "mvn clean -f Diksha"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f Diksha"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f Diksha"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f Diksha"
            }
        }
    }
}
