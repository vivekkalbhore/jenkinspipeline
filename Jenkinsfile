node() {
   def mvnHome
   stage('Preparation') { 
      
      git 'https://github.com/vivekkalbhore/NewJenkinsPipeline.git'
                
      mvnHome = tool 'M3'
   }
   stage('Build') {
      
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
