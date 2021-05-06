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
                            az deployment sub create --name "rg1" --location "West Europe" --template-file template.json --parameters template.parameters.json 
                            
                
                '''
            }
        }
    }
}
