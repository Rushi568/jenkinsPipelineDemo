pipeline {
    agent any
environment
{
    name= "RUSHI TRIVEDI"
}
parameters
{
    string(name: 'person', defaultValue: 'XYZW', description: 'who are you?' )
    booleanParam(name: 'isTrueorFalse', defaultValue:true, description:"")
    choice(name: 'City', choices: ['A','B','C', 'D'],description:"")
    
    
}
    stages {
        stage('TEST') {
            steps {
                echo 'TEST DONE'
            }
        }  
        stage('BUILD') {
            environment
{
    name= "RUSHI TRIVEDI BUILD"
}
            steps {
                echo 'BUILD DONE'
                sh '''
                date
                ls
                pwd
                whoami
                echo "${BUILD_ID}"
                echo "${name}"
                '''
            }
        }
        stage('Deploy on test') {
            environment
{
    name= "RUSHI TRIVEDI deploy to test"
}
            steps {
                echo 'DEPLOY ON TEST'
                echo "${name}"
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'DEPLOY ON PROD'
                echo  "${name}"
        }    }
        stage('Parameter') {
            steps {
                
                echo  "${person}"
                
        }    }
        stage('Continue') {
            input
            {
                message "SHOULD WE CONTINUE?"
                ok "YES WE SHOULD"
            }
            steps {
                
                echo  "ok deploy to prod"
                
        }    }
    }
 post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure
        {
          echo "failure"    
        }
        
        
        success
    {
        echo "success"
    }
}
}
