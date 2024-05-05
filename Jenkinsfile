pipeline {
    agent {
        label 'node1'
    }
    stages {
        stage('Fetch and Clean') {
            steps {
                 bat "mvn clean"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test"
            }
        }
        stage('Package maven job') {
            steps {
                bat "mvn package"
            }
        }
        stage('Run maven job') {
            steps {
                bat "java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App"
                    
            }
        }

    }
}
