  pipeline {
    agent any
    stages {
       stage('Build') {
           steps {
             node('slave1') {      
               sh 'mvn clean package'
                          }
		}
		
    }  
}
}

