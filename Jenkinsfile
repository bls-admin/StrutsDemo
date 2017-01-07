node {
   def mvnHome
   stage('Preparation') { 

      git 'https://github.com/bls-admin/StrutsDemo.git'
     
      mvnHome = tool 'M339'
   }
   stage('Build') {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" clean package/)
      }
   }
   stage('Results') {
      archive 'target/*.war'
   }
}