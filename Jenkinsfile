node {
    def mvnHome 
    def mvnCmd
    def abc=10
         stage ('dev') {
            echo "hello world" 
            echo "your enterred number is: ${abc}"
            git credentialsId: 'github', url: 'https://github.com/pradeepnetha/universalSampleWarFile.git'
            //git credentialsId: 'gitlab', url: 'https://gitlab.com/opstree/Continous-Integration.git'
            //git credentialsId: 'gitlab', url: 'https://gitlab.com/opstree/Continous-Integration.git'
            
        }
        stage ('compile') {
            //echo "${mvnHome}"
            mvnHome=tool  name:'maven',type:'maven'
            mvnCmd="${mvnHome}/bin/mvn"
            sh "${mvnCmd} clean compile "
            //sh "mvn compile"
            echo "you path is $mvnCmd"
        }
        
        stage ('validate') {
            
            sh "${mvnCmd} validate"
           // sh "mvn validate"
        }
        
        stage ('compile') {
            sh "${mvnCmd} compile"
            //sh "mvn compile"
        }
        
        stage ('test') {
            sh "${mvnCmd} test"
            //sh "mvn test"
            echo "this is test"
        }
        
        stage ('package') {
            sh "${mvnCmd} package"
            //sh "mvn package"
            echo "this is package"
        }
        
        stage ('deploy') {
            //sh "mvn deploy"
            sh "${mvnCmd} deploy"
             //nexusArtifactUploader artifacts: [[artifactId: 'univer', classifier: '', file: '/var/lib/jenkins/pipeline/target/', type: 'war']], credentialsId: 'c7605340-2f7f-4763-ba7b-2422b7c60172', groupId: 'universal', nexusUrl: 'http://192.168.122.85:8081/repository/pradeep/', nexusVersion: 'nexus2', protocol: 'http', repository: 'pradeep', version: '1.1'"
            // nexusArtifactUploader artifacts: [[artifactId: 'sampleapp', classifier: 'war', file: '/var/lib/jenkins/workspace/pipeline/target/', type: 'war']], credentialsId: 'c7605340-2f7f-4763-ba7b-2422b7c60172', groupId: 'opstree', nexusUrl: 'http://192.168.122.85:8081/repository/pradeep/', nexusVersion: 'nexus2', protocol: 'http', repository: 'pradeep', version: '1.0'
           // nexusArtifactUploader artifacts: [[artifactId: 'univer', classifier: '', file: '/var/lib/jenkins/workspace/pipeline/target/', type: 'war']], credentialsId: 'dbb94d75-0184-45f8-9177-8a439134b98e', groupId: 'universal', nexusUrl: 'http://192.168.122.85:8081/', nexusVersion: 'nexus2', protocol: 'http', repository: 'pradeep', version: '1.1'
                    }
}
    
