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
				cp /var/lib/jenkins/workspace/ppipeline/dbchk.py /dbtest/
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'this is deploy'
				python /dbtest/dbchk.py
            }
        }
    }
}
