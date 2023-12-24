node{
    stage('Source Code Management (SCM) Checkout'){
        git branch: 'main', url: 'https://github.com/Ganesh-Jayasamraj/DevOps-test.git'
    }
    
    stage('Maven Build Stage'){
        def mvnHome = tool name: "maven", type: "maven"
        sh "${mvnHome}/bin/mvn clean package"
	        sh 'mv target/demo-0.0.1-SNAPSHOT.war target/newsapp.war'
    }
    
    stage("Docker Build Image"){
        sh "docker build -t myapp1 ."
    }
    
    stage("Docker Deploy"){
        sh "docker run -d -p 8090:8080 --name app1 myapp1"
    }
}