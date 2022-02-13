pipeline {
    agent {
        any
    }
    tools {
        maven 'Maven'
        jdk 'Java11'
    }
    parameters {
        // If a parameter name case-insensitively matches an environment variable, the environment variable during the karate test will be null.
        string(name: 'NUM_RES_TO_CREATE', defaultValue: '10', description: 'Max Value 10')
        string(name: 'NUM_PREWRITE_TO_CREATE', defaultValue: '10', description: 'Max Value 10')
        string(name: 'ENVIRONMENT', defaultValue: 'int', description: 'int is only option now.')
    }
    stages {
        stage('build') {
            steps {
              echo 'building the application'
            }
        }

        stage('test') {
            steps {
                echo 'testing the application'
            }
        }

        stage('deploy') {
            steps {
                echo 'deploying the application'
            }
        }
    }
}