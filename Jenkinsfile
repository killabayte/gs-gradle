node {
  def GContainer = docker.image('gradle:jdk8')
  GContainer.pull()
  stage('Preparation') {
    checkout scm
  }
  stage('Testing') {
     GContainer.inside("-v ${env.HOME}/.gradle:/home/gradle/.gradle") {
       sh 'cd complete && ./gradlew test'
     }
  }
  stage('Runing') {
     GContainer.inside("-v ${env.HOME}/.gradle:/home/gradle/.gradle") {
       sh 'cd complete && ./gradlew run'
     }
  }
}
