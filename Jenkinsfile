pipeline {
    agent any
    stages {
        stage("git checkout") {
          steps {
              git 'https://github.com/Amos87/DevOpsClassCodes'
            }
        }
        stage("AB Compile") {
            steps {
                sh 'mvn compile'
            }
        }
        stage("AB Review") {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        stage("AB JUnit_Test") {
            steps {
                sh 'mvn test'
            }
        }
        stage("AB CodeCoverage") {
            steps {
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
        stage("AB Package") {
            steps {
                sh 'mvn package'
            }
        }
        
    }
        
}
