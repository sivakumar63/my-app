node{
   stage('SCM Checkout'){
     git credentialsId: 'siva63', url: 'https://github.com/sivakumar63/my-app.git'
      
   }
   stage('Build'){
     sh  "mvn clean package"
   }
   
   stage('email-notificaiton'){
      
      mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'jenskins build status ', to: 'k.r.rao@outlook.com'
      
      
      
   }
   
   
}
