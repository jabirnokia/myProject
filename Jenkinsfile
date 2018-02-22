pipeline {
  agent { label 'linux'}
  tools {
    maven 'M2'
  }
  stages {
   stage("checkout"){
    steps {
      git "https://github.com/jabirnokia/myProject.git"
    }
   }
   stage('build') {
     steps {
       sh 'mvn clean compile'
     }
   }
   stage('Test') {
     steps {
       sh 'mvn test'
       junit '**/target/surefire-reports/Test-*.xml'
     }
   }
   stage('Package') {
     steps {
       sh 'mvn package'
     }
   }
  }
}
