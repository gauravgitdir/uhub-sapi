pipeline {
  agent any
  stages {
    stage('Build Application') {
      steps {
        bat ' clean install'
      }
    }
    stage('Test') {
      steps {
        echo ' Application in Testing Phase…'
        bat ' test'
      }
    }
    stage('Deployment') {
      environment {
        ENVIRONMENT = 'dev'
        APP_NAME = 'uho-dev-sapi'
      }
      steps {
        echo ' Deploying mule project due to the latest code commit…'
        echo ' Deploying to the configured environment….'
        rc = bat  clean package deploy -Pdev -DmuleDeploy -Dusername=mani_uho -Dpassword=Manimani1 -Denc.key=qwerty987654321 -Danypoint.platform.client_id=b5380b80479645308fa3c1853e314501 -Danypoint.platform.client_secret=248844e0C9124EAfa4eE6ceAE070d752 ' 
        println rc  
      }
    }
  }
}
