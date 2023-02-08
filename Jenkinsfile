pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        
        stage('Deploy to tomcat server'){
            steps{
                deploy adapters: [tomcat9(credentialsId: '32963ee3-7574-41e3-9113-49c9cd26df1a', path: '', url: 'http://43.201.19.50:8088')], contextPath: null, war: '**/*.war'            
            }
        }
    }
}
