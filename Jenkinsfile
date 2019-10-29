node{
    stage('SCM-Checkout'){
        git (url: 'https://github.com/vinperumalla/Maven.git', branch: 'master', credentialsId: 'git-login')
    }
    stage('Compile-Package'){
        def maven = tool name: 'maven', type: 'maven'
        sh '''
        mvn package
    
        '''
    }
}
