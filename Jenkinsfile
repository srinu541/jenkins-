  pipeline {
    agent any
    stages {
       stage('Build') {
           steps {
             node('slave1') {      
               sh 'mvn clean package'
			   sh label: '', script: 'sudo docker image build -t devi .'
			   sh label: '', script: 'sudo docker container run -it -d -p 9999:8080 devi:latest'
                          }
		}
		
    }  
}
}

