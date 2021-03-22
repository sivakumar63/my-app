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
 
   stage('upload-arti-s3'){  
      s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 's3bukeeta', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'ap-south-1', showDirectlyInBrowser: false, sourceFile: '**/*.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 's3bukeeta', userMetadata: []

   } 
}
