node {
    docker.image('maven:3.9.2-eclipse-temurin-17-alpine').inside('-v /root/.m2:/root/.m2') {

        stage('Build') {
            checkout scm
            sh 'mvn -B -DskipTests clean package'
        }

        stage('Test') {
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }
    }
}
