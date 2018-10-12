pipeline {
    agent any 
    stages {
        stage('one') {
            steps {
                echo 'Hi, This is Dinesh'
            }
        }
        stage('Two') {
            steps {
                input('Do you want to proceed?')
            }
        }
        stage ('Three') {
            parallel {
                stage ('Unit Test') {
                    steps (
                        echo "Running the unit test..."
                    }
            }
                        stage ('Integration test') {
                            agent {
                                Docker {
                                    resuseNode false 
                                    image'ubuntu'
                                }
                            }
                        }
         }
      }
 }
