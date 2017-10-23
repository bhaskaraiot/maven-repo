pipeline {
	agent any
	
	stages {
		stage ('Compile Stage') {
			steps {
				withMaven(maven : 'apache-maven'){
					sh 'mvn clean compile'
				}
			}
		}

		stage ('Testing Stage') {
			steps {
				withMaven(maven : 'apache-maven'){
					sh 'mvn test'
				}
			}
		}
		stage ('Installing Stage') {
			steps {
				withMaven(maven : 'apache-maven'){
					sh 'mvn install'
				}
			}				
		}	
		stage ('Deployment Stage') {
			steps {
				withMaven(maven : 'apache-maven'){
					sh 'mvn deploy'
				}
			}				
		}

	post {
	    failure {
	        mail to: 'bhaskaraiot@gmail.com',
	             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
	             body: "Something is wrong with ${env.BUILD_URL}"
    		    }
	      }

	}
}
