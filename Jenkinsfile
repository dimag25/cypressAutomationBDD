
pipeline {
    agent any
    stages {
        stage('cypress parallel tests') {
            parallel {
                stage('tester A') {
                    steps {
                        bat 'npm run cy:run:dashboard'
                    }
                }

                stage('tester B') {
                    steps {
                        bat 'npm run cy:run:dashboard'
                    }
                }
            }
        }
    }
}
