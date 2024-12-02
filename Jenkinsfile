pipeline {
    agent any

    options{
        ansiColor('xterm')
    }

    parameters{
        choice(name: 'ENV', choices: ['dev', 'prod'], description: 'Pick environment')
        choice(name: 'APP_NAME', choices: ['frontend', 'backend'], description: 'Choose APPLICATION')
        string(name: 'app_version', defaultValue: '', description: 'choose version to deploy')
    }
    stages{
        stage('Deployment'){
            steps{
                dir('APP'){
                git branch: 'main', url: 'https://github.com/kp3073/${APP_NAME}'
                }
                dir('HELM'){
                sh 'ENV'
//                 git branch: 'main', url: 'https://github.com/kp3073/expense-helmchart'
//                 sh 'helm upgrade -i ${APP_NAME} . -f ${WORKSPACE}/APP/helm/${ENV}.yaml --set appVersion=${version}'
                
                }            
            }
        }
    }
    post{
        always{
        cleanWs()
        }
    }
}


