pipeline {
    agent any
    tools {
        maven 'Default'
        jdk 'Default'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                sh 'pwd' 
            }
            post {
                success {
                    echo "SUCCESS"
                    echo "Copying html files"
                    sh '''
                        pwd
                        cp *.html /var/www/desi-sas/
                        cp -r img /var/www/desi-sas/
                    '''
                    echo "Done copying html files"
                    echo "Deploying app server"
                }
            }        
        }
    }
}
