pipeline {
  agent any

  triggers { pollSCM('* * * * *') }

  stages {
    stage("Compile") {
      steps {
        sh "./gradlew compileJava"
      }
    }

    stage("Unit test") {
      steps {
        sh "./gradlew test"
      }
    }

    stage("Build") {
      steps {
        sh "./gradlew build"
      }
    }

    stage("DockerBuild") {
      steps {
        sh "docker build -t testdocker ."
      }
    }

  }
}