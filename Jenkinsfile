pipeline {
    agent any
	tools {
        maven 'Maven 3.5.3'
        jdk 'JDK1.8'
		}

    stages {
        stage('Build') {
            steps {
                 sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                 sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
			  
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
        }
   
    }
}
}