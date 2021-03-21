pipeline {
	agent none
	stages {
		stage('Non-Parallel Stage') {
			agent {
				label "master"
			}
			steps {
				echo 'This stage wil be executed first'
			}
		}
		
		stage('Run Test') {
			parallel {
				stage('Test On Windows') {
					agent {
						label "Windows Node"
					}
					steps {
						echo 'Task1 on Agent'
					}
				}
				stage('Test on master') {
					agent {
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
