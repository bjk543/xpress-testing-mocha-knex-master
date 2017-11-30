parallel (
    "database" : { 
                     node { 
                         stage('Checkout'){
                           checkout scm
                           timeout(time: 3, unit: 'MINUTES') {
                           sh 'docker-compose up'
                            }
                         }
                       } 
                   },
    "test" : { 
                     node { 
                           stage('Checkout'){
                           checkout scm
                           sh 'npm install'
                            
                           retry(3) {
                            sh 'npm test'
                             }
                         }                                                   
                       } 
                   }
          )