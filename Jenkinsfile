node{

        stage ('OWASP Dependency-Check Vulnerabilities ') {
           
                deleteDir()
              
                checkout([$class: 'GitSCM', branches: [[name: '*/$branchName$']], extensions: [], userRemoteConfigs: [[credentialsId: '$gitCredsId$', url: '$giturl$']]])
                bat 'mvn compile'
               
                dependencyCheck additionalArguments: ''' 
                   -o "./" 
                    -s "./"
                   -f "ALL" 
                    --prettyPrint''', odcInstallation: '$owaspInstallConfig$'

                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
               
        
        
    }
}
