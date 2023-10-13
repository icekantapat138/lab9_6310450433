pipeline {
     agent {
          docker {
               image 'maven:3-jdk-17'  
               args '-p 33333:8090' 
          }
     }
     environment {
          HOME = '.'
     }
     stages {
          stage('Source') {
               steps {
                    git branch: 'main',
                        url: 'https://github.com/boonblablabla/wisdom-book.git'
               }
          }
          stage('Build') {
               steps {
                    bat 'mvn package -DskipTests'
               }
          }
          stage('Test') {
               steps {
                    echo 'testing...'
               }
          }
          stage('Deploy') {
               steps {
                    bat 'java -jar ./target/book-1.0.jar'
               }
          }
     }
}
