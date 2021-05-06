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
                            
                            az login
                            az account show
                            az deployment create \
                            -n demoEmptyRG \
                            -l southcentralus \
                            --template-file "$WORKSPACE/template.json"
                            --parameters "{ \"rgLocation\": { \"value\": \"westus\" } }"
                            --parameters "{ \"rgName\": { \"value\": \"demoRG\" } }"
                            
                
                '''
            }
        }
    }
}
