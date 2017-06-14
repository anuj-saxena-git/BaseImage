node {
    def app

    stage('Build base image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
  
      //  app = docker.build("getintodevops/hellonode")
     //   app = docker.build("anuj-saxena-git")
        app = docker.build("anujsaxenadocker90/anuj-saxena-git")
        
        
      //  sh 'app = docker.build("getintodevops/hellonode") '
        
      //  sh 'sudo docker.build("anuj-saxena-git/DockerExample") '
      
    }
    
   /* stage('Push image') {
        //* Finally, we'll push the image with two tags:
        // * First, the incremental build number from Jenkins
        // * Second, the 'latest' tag.
       //  * Pushing multiple tags is cheap, as all the layers are reused. 
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
     //       docker.withRegistry('https://hub.docker.com/r/anujsaxenadocker90/samplerepo/', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
        
        
    } */
    
    stage('Push image to ECR') {
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. */
        docker.withRegistry('https://848859896798.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:anuj-ecr-credentials') {
     //       docker.withRegistry('https://hub.docker.com/r/anujsaxenadocker90/samplerepo/', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
        
    }
}
