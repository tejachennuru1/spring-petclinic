pipeline {
    agent { label 'dotnet' }
        stages {
            stage('vcs') {
                steps {
                    git branch: 'main', url: 'https://github.com/tejachennuru1/spring-petclinic.git'
                }
            }
        stage('build') {
                steps {
                    sh 'mvn package'
                    sh './mvn build'
                }
        }
        stage('archive results') {
                steps {
                    junit '**/target/surefire-reports/*.xml'
                }
        }
        stage('artifacts') {
                steps {
                    archiveArtifacts artifacts:  '**/target/*.jar'
                }
        }
        }
}
