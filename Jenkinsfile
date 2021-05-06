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
                            ############################### shell #############################   
                            
                            $Env:SYSTEM_DEFAULTWORKINGDIRECTORY = $env:WORKSPACE
                            $scriptRoot = $( $Env:SYSTEM_DEFAULTWORKINGDIRECTORY  )
                            Set-Location $scriptRoot
                            $ErrorActionPreference = "Stop"
                            
                            az login
                            az account show
                            az deployment create \
                            -n demoEmptyRG \
                            -l southcentralus \
                            --template-file Template.json \
                            --parameters Template.parameters.json
                            
                
                '''
            }
        }
    }
}
