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
                        credentialsId: 'token',
                        usernameVariable: 'MY_USER',
                        passwordVariable: 'MY_PASSWORD'
                    )
                ]){
                    sh '''
                        echo "my user name is $MY_USER"
                        echo " my password is $MY_PASSWORD"
                    '''
                }
            }
        }
    }
}