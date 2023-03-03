pipeline {
    agent{ lable 'UBUNTU_NODE2' }
    stages{
        stage('vcs'){
            steps{
                git branch: 'declarative' , url: 'https://github.com/Shravanipranay/openmrs-core.git'
            }
        }
        stage('build'){
            steps{
                sh 'export PATH=/usr/lib/jvm/java-1.8.0-openjdk-amd64:$PATH'
                sh 'mvn package'
            }
        }
        stage('archiving artifacts'){
            steps{
                archiveArtifacts artifacts : '**/openmrs-liquibase-2.7.0-SNAPSHOT-tests.jar'
                                    junit '**/*.xml'

            }
        }

    }
}