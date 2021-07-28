node("maven") { 
    stage('Compile') {
        sh 'git clone https://github.com/FlorinPeter/Spring-Boot-Sample-Project.git'
        sh 'cd Spring-Boot-Sample-Project;pwd;ls -la'
        sh 'cd Spring-Boot-Sample-Project;mvn clean package -DskipTests=true'
    }
    stage('Unit Tests') {
        sh 'cd Spring-Boot-Sample-Project;mvn surefire:test'
    }
     stage('Integration Tests') {
        sh 'cd Spring-Boot-Sample-Project;mvn failsafe:integration-test'
        junit 'Spring-Boot-Sample-Project/target/surefire-reports/TEST-*.xml'
    }
}
