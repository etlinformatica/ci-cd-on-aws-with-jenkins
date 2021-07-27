pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
            }
    tools {
        maven 'Maven'
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'building the application…'
                echo "building version ${NEW_VERSION}"
                sh "mvn install"
            }
        }
        stage('Test'){
            when {
                expression {
                    BRANCH_NAME == 'dev'
                            }
                }
            steps {
                echo 'testing the application…'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploying the application…'
                
            }
        }
    }
}
