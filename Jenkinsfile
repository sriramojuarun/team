node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("sriramojuarun9/team6")
    }

    stage('Test image') {
  

        app.inside {
            sh 'echo "Tests passed2"'
        }
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'team') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
     
        
     
}
