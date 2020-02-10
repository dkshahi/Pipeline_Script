pipeline {
    agent none
    stages {
        
        stage('Non-Parallel Stage') {
            agent {
                        label "master"
                }
            steps {
                        echo 'This stage will be executed first'
                }
            }
    
    stage('Run Tests') {
        parallel {
            stage('Test On Windows') {
                agent {
                        label "win_jenkins_slave_01-c497514b"
                }
                steps {
                        echo "Task1 on Windows Agent Node"
                }
            }
            stage('Test On Master') {
                agent {
                    label "master"
                }
                steps {
                        echo "Task1 on Windows Master Node"   
                }
            }
        }
    }
}
}
