node {
  stage("Clone the project") {
    git branch: 'master', url: 'https://github.com/Debidattanayak/jenkins-maven-pipeline-sample.git'
  }

  stage("Compilation") {
    sh "mvn clean install"
  }

  stage("Tests and Deployment") {
    stage("Runing unit tests") {
      sh "mvn test -Punit"
    }
    stage("Deployment") {
      sh 'mvn spring-boot:run -Dserver.port=8083 &'
    }
  }
}
