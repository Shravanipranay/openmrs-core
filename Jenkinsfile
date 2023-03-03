node('UBUNTU_NODE2'){
    stage('vcs'){
        git branch: 'scripted', url: 'https://github.com/Shravanipranay/openmrs-core.git'
    }
    stage('build'){
         sh 'export PATH=/usr/lib/jvm/java-1.8.0-openjdk-amd64:$PATH'
         sh 'mvn package'
    }
    stage('archiving artifacts'){
        archiveArtifacts artifacts : '**/openmrs-liquibase-2.7.0-SNAPSHOT-tests.jar'
                         junit '**/*.xml'
    }
}