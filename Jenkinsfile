node(master){
    stage('Contdownload'){
        git 'https://github.com/komatla93/CICDPractice.git'
    }
    stage('Contbuild'){
        sh 'mvn package'
    }
    stage('Contdeployment'){
        sh 'scp /home/ubuntu/.jenkins/workspace/SPipeline/webapp/target/webapp.war ubuntu@172.31.11.138:/var/lib/tomcat9/webapps/test01.war'
    }
    stage('Conttesting'){
        git 'https://github.com/komatla93/FunTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/SPipeline/testing.jar'
    }
    stage('Contdelivery'){
         sh 'scp /home/ubuntu/.jenkins/workspace/SPipeline/webapp/target/webapp.war ubuntu@172.31.21.215:/var/lib/tomcat9/webapps/prod01.war'

    }
}
