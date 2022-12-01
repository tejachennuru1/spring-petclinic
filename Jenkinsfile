pipeline {
    agent { label 'proj1' }
        stages {
            stage('vcs') {
                steps {
                    git branch: 'main', url: 'https://github.com/tejachennuru1/spring-petclinic.git'
                }
            }
        stage('build') {
                steps {
                    sh 'mvn package'
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
