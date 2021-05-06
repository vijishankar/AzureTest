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
                            az deployment sub create \
                            -n demoEmptyRG \
                            -l southcentralus \
                            --template-file template.json
                            --parameters rgName=demoRG rgLocation=northcentralus
                            
                
                '''
            }
        }
    }
}
