/* compile war on master and install tomcat server on slaves 1,2

*/
pipeline{
    agent{
        node{
        label 'master'
        customWorkspace '/mnt/hello-word'
        }
    }

	stages{
		stage ('parallel stage'){
		parallel{
		stage('compiled war on master'){
			steps{
			sh '/mnt/tools/apache-maven-3.8.7/bin/mvn clean install'
			}
		}
/**		stage('download/unzip tomcat on slave1'){
			agent {
				label 'slave1'
			}
			steps{
			dir('/mnt/tools'){
			sh 'wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.70/bin/apache-tomcat-9.0.70.zip'
			sh 'unzip apache*tomcat*.zip'
			sh 'chmod +x apache*tomcat*/bin/*'
			}
			}
		} **/
/**		stage('download/unzip tomcat on slave 2'){
			agent {
				label 'slave2'
			}
			steps{
			dir('/mnt/tools'){
			sh 'wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.70/bin/apache-tomcat-9.0.70.zip'
			sh 'unzip apache*tomcat*.zip'
			sh 'chmod +x apache*tomcat*/bin/*'
			}
			}
		} **/
		}
		}
	}
}
