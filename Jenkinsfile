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
                            --template-uri https://raw.githubusercontent.com/Azure/azure-docs-json-samples/master/azure-resource-manager/emptyRG.json \
                            --parameters rgName=demoRG rgLocation=northcentralus
                            
                
                '''
            }
        }
    }
}
