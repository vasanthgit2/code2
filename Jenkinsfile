import java.net.URL
import hudson.model.*
node{
    stage('Git CHECK OUT'){
        git'https://github.com/edureka-git/DevOpsClassCodes.git'
    }
    stage('Compile'){
        withMaven(maven:'MavenTest'){
            sh 'mvn compile'
        }
    }
    stage('Test'){
        try{
            withMaven(maven:'MavenTest'){
                sh 'mvn test'
            }
        }   finally{
            junit 'target/surefire-reports/*.xml'
        }
    }
    stage('Package'){
        withMaven(mavne:'MavenTest'){
            sh 'mvn package'
        }
    }
    
    
}
    
    
   
