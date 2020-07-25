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
         sh """mvn sonar:sonar \
  -Dsonar.projectKey=petclinic \
  -Dsonar.host.url=http://192.168.0.112:9000/ \
  
  -Dsonar.login=4c05eeee47f07f20c1bd4be2496ce8fe00aed680
  -Dcheckstyle.skip
  """
   
       
}
}
