pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                echo 'this is build' 
            }
        }
        stage('Test'){
            steps {
                echo 'this is test'
				sh "/usr/bin/cp -u /var/lib/jenkins/workspace/ppipeline/dbchk.py /dbtest/"
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'this is deploy'
				sh "/usr/bin/python /dbtest/dbchk.py"
            }
        }
    }
}
