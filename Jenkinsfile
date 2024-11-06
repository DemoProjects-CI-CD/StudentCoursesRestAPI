pipeline {
    agent { label 'MVN' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage ('user') {
            sh 'whoami'
        }
        stage ('VCS') {
            steps {
                git url: 'https://github.com/DemoProjects-CI-CD/StudentCoursesRestAPI.git',
                    branch: 'declarative'
            } 
        }
        stage ('build') {
            steps {sh 'docker image build -t vishnuvardhanduvuri/studentcourse:latest .'}       
        }
        stage ('Push') {
            steps {
                sh 'docker image push vishnuvardhanduvuri/studentcourse:latest'
            }
        }
    }
}
