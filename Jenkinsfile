pipeline{
    agent{label 'master'}
    tools{maven 'maven-3.9.4'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/mnidevops/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
