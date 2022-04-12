node{

        stage ('OWASP Dependency-Check Vulnerabilities') {
           
                deleteDir()
              
                checkout([$class: 'GitSCM', branches: [[name: '*/']], extensions: [], userRemoteConfigs: [[credentialsId: '$gitCredsId$', url: 'https://github.com/charankk21/simplistic.rabbitMQ_sca.git']]])
                bat 'mvn compile'
               
                dependencyCheck additionalArguments: ''' 
                   -o "./" 
                    -s "./"
                   -f "ALL" 
                    --prettyPrint''', odcInstallation: ''

                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
               
        
        
    }
}
