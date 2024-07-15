pipeline {
    agent {
       node {
         label 'agent-1' 
     }
}
   environment { 
      packageVersion = ' '
      nexusURL = '172.31.43.110:8081'
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()
    }
      
    parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

       booleanParam(name: 'Deploy', defaultValue: false, description: 'Toggle this value')

    //     choice(name: 'action', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

//   build
    stages {
        stage('get the version') {
            steps {
                script {
                        def packageJson = readJSON file: 'package.json'
                            packageVersion = packageJson.version
                            echo "application version: $packageVersion"
               }
            }
        }
    }     
    
    //  post build 
     post { 
        always { 
            echo 'I will always say Hello again!'
             deleteDir()
        }
     

        failure {
            echo ' this runs when pipeline is failed used generally to send alerts'
        }
      
       success { 
            echo 'I will always say Hello when pipeline is success'
        }
   
    }
}