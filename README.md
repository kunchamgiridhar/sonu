groovy
pipeline {
agent any
stages {
stage('Build') {
steps {
git 'https://github.com/kunchamgiridhar/sonu.git'
sh 'mvn clean install'
}
}
stage('Test') {
steps {
sh 'mvn test'
}
}
stage('Deploy') {
steps {
sh 'deploy.sh'
}
}
}
}
