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
				sh "rm -rf /dbtest/dbchk.py"
				sh "rm -rf /dbtest/dbdata.py"
				sh "/usr/bin/cp  /var/lib/jenkins/workspace/ppipeline/dbchk.py /dbtest/"
				sh "/usr/bin/cp  /var/lib/jenkins/workspace/ppipeline/dbdata.py /dbtest/"
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'this is deploy'
				sh "/usr/bin/python /dbtest/dbchk.py"
				sh "/usr/bin/python /dbtest/dbdata.py"
				sh "/usr/bin/python /dbtest/dbdata.py"
            }
        }
    }
}
