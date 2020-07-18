node{
   stage('scm checkout'){
   git 'https://github.com/madhuprasadbm/test'
   }
   stage('compile package'){
   def mvnhome = tool name: 'maven3', type: 'maven'
   sh "${mvnhome}/bin/mvn package"
   }
   stage('email notification'){
      mail bcc: '', body: '''HI bro
      test email from jenkins
      Thanks''', cc: '', from: '', replyTo: '', subject: 'Jenkins notification', to: 'madhuprasad.bm@gmail.com'
}
}
   
   
