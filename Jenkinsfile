  pipeline {
          agent { label 'slave1'}
        stages {
          stage('Build') {
             steps {      
               sh 'mvn clean package'
                    }
		}
		
    }  
}


