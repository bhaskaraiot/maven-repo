pipeline {
agent any

stages {

stage('compile stage') {
steps {
withMaven(maven : 'apache-maven-3.5.0'
          sh 'mvn clean compile'
}
}
stage ('Testing Stage') {

steps {
withMaven(maven : 'apache-maven-3.5.0'
          sh 'mvn test'
}
}
          stage ('Installing Stage') {

steps {
withMaven(maven : 'apache-maven-3.5.0'
          sh 'mvn install'
}
}
stage ('Development stage'){
steps {
withMaven(maven : 'apache-maven-3.5.0'
          sh 'mvn deploy'
}
}
}
}
          }
