node{
   stage('SCM Checkout'){
      git credentialsId: 'siva63', url: 'https://github.com/sivakumar63/my-app.git'
      
   }
   stage('Build'){
      sh  "mvn clean package"
    
   }
    
   stage('Deploy-Tom'){
      deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://65.1.92.168:8080')], contextPath: 'my-app', onFailure: false, war: '**/*.war'
   
   }
   stage('email-notificaiton'){
      
      mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'jenskins build status ', to: 'sivakumarkare6363@gmail.com'
      
      
      
   }
   
   
}
