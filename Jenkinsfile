pipeline{
	agent any
	tools {
		jdk '1.8.0_252'
	}
	options {
		timestamps()
		
	}
	stages {
		stage('Display the path of jenkins'){
			steps {
				echo "this is building an job"
				echo "PATH = ${PATH}"
			}
		}
		stage('check the source code'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Nirmalraaj/Jenkins.git']]])
			}
		}
		stage('run the python code'){
			steps {
				sh 'python test.py'
			}
		}
		stage('email notifictaion'){
			steps {
				mail bcc: '', body: 'Hi error has occured', cc: '', from: '', replyTo: '', subject: 'Jenkins Pipeline', to: 'nirmal11.12.1998@gmail.com'
	
			}
		}
	}
}
