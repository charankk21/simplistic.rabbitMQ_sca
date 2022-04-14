node{
    
 
   stage('SetEnv') { 
      git 'https://github.com/charankk21/simplistic.rabbitMQ_sca.git'
	   
   }
   

   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: 'test', snykInstallation: 'rwtw', snykTokenId: 'tewt'
       
   }

}