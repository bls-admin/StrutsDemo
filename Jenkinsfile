node {
   def mvnHome
   stage('Preparation') { 

      git 'https://github.com/bls-admin/StrutsDemo.git'
     
      mvnHome = tool 'M339'
   }
   stage('Build') {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      archive 'target/*.jar'
   }
}