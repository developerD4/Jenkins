pipeline{
  agent any

  tools{
    maven 'MAVEN_HOME'
  }
  stages{
    stage('Checkout'){
      steps{
        git branch: 'branch',url:'https://github.com/developerD4/Jenkins.git', git credentialsId:  'Git-logIn-access'
      }
    }
    stage('Built'){
      steps{
        bat 'maven clean install'
      }
    }
    stage('Test'){
      steps{
        test 'mvn test'
      }
    }
    stage('Package'){
      steps{
        //bat 'mvn package'
        echo 'Package created'
      }
    }
    stage('Deploy'){
      steps{
        echo 'Deployed successfully'
        //bat 'copy '
      }
    }
  }
  Post{
    failure{
      echo 'Built Failed'
    }
    success{
      echo 'Buil Successed'
    }
  }
}
