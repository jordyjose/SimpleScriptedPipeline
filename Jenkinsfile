pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "master"
                }
        steps {
                echo 'This stage will be executed first'
		echo 'Eg: Consider this steps as summary for pulling from GIT, Building and Testing'
                echo 'The next stage is to deply on tested code on different machines likes windows, linux etc for the next steps, whihc will be done in PARALLEL'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Linux') {
                    agent {
                        label "Linux_Node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "master"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
