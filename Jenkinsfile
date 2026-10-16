pipeline{
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java21'
    maven 'maven3'
  }

stages{
  stage("1. Cleanup Workspace"){
    steps {
      cleanWs()
    }
  }

  stage("2. Checkout for SCM"){
    steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/AnkitaPandey23/Register-App.git'
    }
  }

  stage("3. Build the Application"){
    steps {
      sh 'mvn clean package'
    }
  }

  stage("4. Test Application"){
    steps{
      sh 'mvn test'
    }
  }

}
}
