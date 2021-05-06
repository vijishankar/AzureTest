pipeline {

    agent any
    
    environment {
        AZURE_ID = credentials('Azure_User_Id')
        AZURE_Password = credentials('Azure_Pass')
    }

    stages {

        stage('LOGGING Azure') {
            steps {
                    sh ''' 
                            ############################### Powershell #############################
                            
                            
                            az login -u $Env:AZURE_ID -p $Env:AZURE_Password 
                            az account show
                
                '''
            }
        }
    }
}
