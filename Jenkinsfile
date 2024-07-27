pipeline {

	agent any
	tools {
 		 maven 'm389'
		}

	stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}

stage('test') {
	steps  {
		sh 'mvn test'
	   }
   	post {
                 archiveArtifacts artifacts: 'target/**.war', followSymlinks: false
                 junit stdioRetention: '', testResults: 'target/surefire-report/*.xml'

    	 	}
}

    }
  }
