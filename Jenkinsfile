pipeline {
  agent { label 'linux'}
  tools {
    maven 'maven'
  }
  stages {
   stage("checkout"){
    steps {
      git "https://github.com/jabirnokia/myProject.git"
    }
   }
   stage('build') {
     steps {
       sh '/usr/share/maven/bin/mvn clean compile'
     }
   }
   stage('Test') {
     steps {
       sh '/usr/share/maven/bin/mvn test'
     }
   }
   stage('Package') {
     steps {
       sh '/usr/share/maven/bin/mvn package'
       archiveArtifact artifacts: 'target/*.jar', fingerprint: true
     }
   }
  }
}
