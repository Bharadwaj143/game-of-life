// node('JDK8') {
//     stage('SourceCode') {
//         // get the code from git repo on the branch sprint1_develop
//         git branch: 'sprint1_develop', url: 'https://github.com/KhajasCICDSamples/game-of-life.git'
//     }

//     stage('Build the code') {
//         sh 'mvn clean package'
//     }

//     stage('Archiving and Test Results') {
//         junit '**/surefire-reports/*.xml'
//         archiveArtifacts artifacts: '**/*.war', followSymlinks: false
//     }

// }

pipeline {
    agent { label 'JDK8' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('SourceCode') {
            steps {
                git branch: 'sprint1_develop', url: 'https://github.com/KhajasCICDSamples/game-of-life.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archive and Test Results') {
            steps {
               junit '**/surefire-reports/*.xml'
               archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}