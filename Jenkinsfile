pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
            }
    parameters {
        //string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'version to deploy on prod')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
        options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'building the application…'
                
                 }
        }
        stage('Test'){
            when {
                expression {
                    params.executeTests == true
                            }
                }
            steps {
                echo 'testing the application…'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploying the application…'
                echo "deploying version ${params.VERSION}"
                
            }
        }
    }
}
