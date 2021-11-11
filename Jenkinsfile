
pipeline {
    agent any
    stages {
        stage('cypress parallel tests') {
            stage('build') {
                    steps {
                        bat 'npm install'
                    }
            }
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
                stage('tester C') {
                    steps {
                        bat 'npm run cy:run:dashboard'
                    }
                }
            }

                stage('allure-reports') {
                        steps {
                    script {
                            allure([
                                                includeProperties: false,
                                                jdk: '',
                                                properties: [],
                                                reportBuildPolicy: 'ALWAYS',
                                                results: [[path: './allure-results']]
                                        ])
                    }
                        }
                }
        }
    }
}
