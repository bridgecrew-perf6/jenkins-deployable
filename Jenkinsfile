pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    parameters {
        // If a parameter name case-insensitively matches an environment variable, the environment variable during the karate test will be null.
        string(name: 'NUM_RES_TO_CREATE', defaultValue: '10', description: 'Max Value 10')
        string(name: 'NUM_PREWRITE_TO_CREATE', defaultValue: '10', description: 'Max Value 10')
        string(name: 'ENVIRONMENT', defaultValue: 'int', description: 'int is only option now.')
    }
    stages {
        stage ('Initialize') {
                steps {
                    sh '''
                        echo "PATH = ${PATH}"
                        echo "M2_HOME = ${M2_HOME}"
                    '''
                }
            }
        stage('build') {
            steps {
              echo 'building the application'
              sh 'mvn clean package'
            }
        }

         stage('test') {
            steps {
              echo 'building the application'
              sh 'mvn -Dtest=JenkinsDeployableApplicationTests test'
            }
        }

        stage('deploy') {
            steps {
                echo 'deploying the application'
            }
        }
    }
}