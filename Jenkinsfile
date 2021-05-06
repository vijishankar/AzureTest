pipeline {

    agent any
    
    environment {
        AZURE_CLIENT_ID = credentials('AZURE_CLIENT_ID_TEST')
        AZURE_CLIENT_SECRET = credentials('AZURE_CLIENT_SECRET_TEST')
        AZURE_TENANT_ID = credentials('AZURE_TENANT_ID_TEST')
        APP_URL = credentials('APP_URL_TEST')
    }

    stages {

        stage('LOGGING THROUGH SERVICE PRINCIPLE') {
            steps {
                    pwsh ''' 
                            ############################### Powershell #############################
                            
                            
                            az login --service-principal -u $Env:APP_URL -p $Env:AZURE_CLIENT_SECRET --tenant $Env:AZURE_TENANT_ID | Out-null
                            az group list
                
                '''
            }
        }
    }
}
