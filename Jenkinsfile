pipeline {
    agent any

    stages {
        stage('clone from github(GitHubBuild)') {
            steps {
                git branch: 'master', url: 'https://github.com/adikesavanaidug2404/Ekart-Deploy-Tomcat.git'
            }
        }
        stage('build war file(MavenBuild)') {
            steps {
                sh "mvn clean install package"
            }
        }
        stage('deploy to tomcat(DeployBuild)') {
            steps {
                sh "sudo scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/deployproject/webapp/target/webapp.war root@44.197.245.35:/opt/apache-tomcat-10.1.18/webapps/"
            }
        }
    }
}
