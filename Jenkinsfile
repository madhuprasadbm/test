node{
   stage('scm checkout'){
   git 'https://github.com/madhuprasadbm/test'
   }
   stage('compile package'){
   def mvnhome = tool name: 'maven3', type: 'maven'
   sh "${mvnhome}/bin/mvn package"
   }
   
   
