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
		}
		}
	}
}
