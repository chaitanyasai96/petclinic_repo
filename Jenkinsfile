node{
    stage("scm"){
        git 'https://github.com/chaitanyasai96/petclinic_repo.git'
    }
    stage('Build'){
        sh 'mvn clean package'
    }
    stage('test'){
        sh 'mvn test'
    }
    stage('Junit test'){
        junit 'target/surefire-reports/*.xml'
    }
    stage('archive'){
        archive 'target/*.jar'
    }
}
