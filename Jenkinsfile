node {
    docker.image('eclipse-temurin:11-jdk-alpine').inside('-v /root/.m2:/root/.m2') {

        stage('Build') {
            echo pwd
            checkout scm
            sh 'mvn -B -DskipTests clean package'
        }

        stage('Test') {
            sh 'mvn test'
            
            junit 'target/surefire-reports/*.xml'
        }
    }
}
