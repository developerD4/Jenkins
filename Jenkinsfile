pipeline{
  agent any

  tools{
    maven 'Maven_Home'
  }
  options{
    skipDefaultCheckout(true)
  }
  stages{
    stage('Checkout'){
      steps{
        git branch: 'branch', url:'https://github.com/developerD4/Jenkins.git', credentialsId:  'Git-logIn-access'
      }
    }
    stage('Built'){
      steps{
        bat 'mvn clean install'
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
  post{
    failure{
      echo 'Built Failed'
    }
    success{
      echo 'Buil Successed'
    }
  }
}
