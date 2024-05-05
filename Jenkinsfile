pipeline {
    agent {
        label 'node1'
    }
    stages {
        stage('Fetch and Clean') {
            steps {
                 bat """
                      cd maven-app
                      mvn clean
                  """.stripIndent().trim()
            }
        }
        stage('Test') {
            steps {
                bat """
                    cd maven-app
                    mvn test
                """.stripIndent().trim()
            }
        }
        stage('Package maven job') {
            steps {
                bat """
                    cd maven-app
                    mvn package
                """.stripIndent().trim()
            }
        }
        stage('Run maven job') {
            steps {
                bat """
                    cd maven-app
                    java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App
                """.stripIndent().trim()
            }
        }

    }
}
