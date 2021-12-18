node{
    stage('git'){
        git branch: 'main', url: 'https://github.com/Sai629/java-demo.git'
    }
     stage('maven'){
      withMaven( jdk: 'java8', maven: 'maven 3') {
         sh 'mvn compile'
      }
    }
   
    stage('test'){
        withMaven( jdk: 'java8', maven: 'maven 3') {
            sh 'mvn test'
      }
    }
    stage('junit'){
        junit '**/*.xml'
    }
    stage('package'){
        withMaven( jdk: 'java8', maven: 'maven 3') {
            sh 'mvn package'
      }
    }
    
    stage('artifactory'){
        archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
    }
}
