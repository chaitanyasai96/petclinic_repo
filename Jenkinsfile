node{
    stage("scm"){
        git 'https://github.com/chaitanyasai96/petclinic_repo.git'
    }
    stage('Build'){
        sh 'mvn clean package -Dcheckstyle.skip'
    }
    stage('test'){
        sh 'mvn test -Dcheckstyle.skip'
    }
    stage('Junit test'){
        junit 'target/surefire-reports/*.xml'
    }
    stage('archive'){
        archive 'target/*.jar'
         sh "mvn sonar:sonar -Dsonar.projectKey=petclinic -Dsonar.host.url=http://18.222.104.159:9000/ -Dsonar.login=28acae71f7d9cff446a94080a4bb6eeeb47af109 -Dcheckstyle.skip"
   
       
}
}
