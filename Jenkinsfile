pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/http"
		}
	}
	stages {
		stage ("install-docker") {
			steps {
				sh "yum install docker -y"
				sh "service docker start"
			}
		}
		stage ("httpd-container-run") {
			steps {
				sh "docker run -dp 80:80 --name server httpd"
				sh "git clone https://github.com/sushil-11-jadhav/23Q1.git"
				sh "docker cp /mnt/http/index.html server:/usr/local/apache2/htdocs"
				
			}
		}
	}
}
