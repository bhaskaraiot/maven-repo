
pipeline {
agent any

stages {

stage('compile stage') {
steps {
withMaven(maven : 'apache-maven'
          sh 'mvn clean compile'
}
}
stage ('Testing Stage') {

steps {
withMaven(maven : 'apache-maven'
          sh 'mvn test'
}
}
          stage ('Installing Stage') {

steps {
withMaven(maven : 'apache-maven'
          sh 'mvn install'
}
}
stage ('Development stage'){
steps {
withMaven(maven : 'apache-maven'
          sh 'mvn deploy'
}
}
}
post {
	always {
	echo 'one way or another, I have finished'
	deleteDir() /*clean up our work space */
	}
	sucess {
	echo 'I succeesed!"
	}
	unstable {
	echo 'I am unstable :/'
	}
	failure {
	echo 'I failed :('
	}
	changed {
	echo 'Things were diffrent before ...'
	
}
}
}
