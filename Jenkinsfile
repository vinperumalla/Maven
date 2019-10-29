node('master'){
    stage('SCM-Checkout'){
        
        git (url: 'https://github.com/vinperumalla/Maven.git', branch: 'master', credentialsId: 'git-login')
    }
    stage('Unit-Test'){

        sh "echo Unit-Test"
    
    }  
    stage('Compile-Package'){
    def maven = tool name: 'maven', type: 'maven'
    sh '''
    chmod 766 *
    ./mvnw clean package
    '''
    }
    stage('Verify-Package'){
        sh '''        
        ./mvnw verify
        '''
    }  
    // stage('Code_Analysis'){
    //     sh '''    
    //     docker-compose -f src/main/docker/sonar.yml up -d
    //     sleep 10s
    //     ./mvnw initialize sonar:sonar
    //     ./mvnw -Pprod clean verify sonar:sonar
    //     docker rm -f $(docker ps -q)
    //     '''
    // }
    stage('Cleanup-Workspace'){
      sh "rm -rf *"
    }    
}
