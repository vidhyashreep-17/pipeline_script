pipeline {
  agent none
  stages {

    stage('Non parallel stage') {
	agent{
		label "master"
	}
      steps {
        echo 'This will be executed first'
      }
    }
    stage('Run Tests') {
	parallel{
		stage('Test on Agent'){
			agent{
			label "Windows_Node"
			}
			steps {
        		echo 'Task1 on Agent'
			}
	
		}

	
		stage('Test on Master') {
      			agent{
			label "master"
			}
			steps {
        		echo 'Task1 on master'
		        }
    		}
        }
    }
     
  }

}
