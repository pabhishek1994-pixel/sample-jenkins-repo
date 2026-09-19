pipeline{
    agent any
    stages {
        stage("list-down-file") {
            steps {
                sh '''
                    pwd
                    ls -lrt
                '''
            }
        }
        stage("print-cred") {
            steps {
                withCredentials([
                    usernamePassword(
                        credentialsId: 'xyz',
                        usernameVariable: 'MY-USER',
                        passwordVariable: 'MY-PASSWORD'
                    )
                ]){
                    sh '''
                        echo "my user name is ${MY-USER}"
                        echo " my password is ${MY-PASSWORD}"
                    '''
                }
            }
        }
    }
}