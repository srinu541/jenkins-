pipeline {
    agent any
    stages {
       stage('Build') {
           steps {
		   node('master'){
               sh 'mvn clean package'
			   sh label: '', script: 'sudo docker image build -t sree .'
			   sh label: '', script: 'sudo docker login -u admin -p admin123 34.213.35.158:8082'
			   sh label: '', script: 'sudo docker tag sree:latest 34.213.35.158:8082/sree:1.0'
			   sh label: '', script: 'sudo docker push 34.213.35.158:8082/sree:1.0'
			   }
		   node('docker slave 1'){
               sh label: '', script: 'sudo docker login -u admin -p admin123 34.213.35.158:8082'
               sh label: '', script: 'sudo docker pull 34.213.35.158:8082/sree:1.0'
               sh label: '', script: 'sudo docker container run -it -p 9999:8080 sree:latest'
		   }
        } 		   
		
    }  
}
}

