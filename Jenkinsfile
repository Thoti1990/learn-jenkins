pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETINGS = 'HEllo Jenkins'
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()
    }

    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo "here i write shell script"
                    echo "$GREETINGS"
                """
                
            }
        }
    }
    // post build
     post { 
        always { 
            echo 'I will always say Hello again!'
        }
         failure { 
            echo 'this runs when pipeline is failed, used generally send some alrts'
        }
         success { 
            echo 'I will say hello when pipeline is success'
        }
    }
}