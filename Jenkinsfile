node{
    stage('git'){
        git branch: 'main', url: 'https://github.com/Sai629/java-demo.git'
    }
     stage('maven'){
      withMaven( jdk: 'java8', maven: 'maven 3') {
         //sh 'mvn compile'
          sh 'echo hello'
      }
    }
   
    stage('test'){
        withMaven( jdk: 'java8', maven: 'maven 3') {
            sh 'echo hi'
      }
    }
    stage('junit'){
        //junit '**/*.xml'
        
        sh 'echo hi'
    }
    stage('package'){
        withMaven( jdk: 'java8', maven: 'maven 3') {
           sh 'echo package'
      }
    }
    
    stage('artifactory'){
        archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
    }
}
