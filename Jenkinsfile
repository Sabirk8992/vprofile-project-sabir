pipeline {
    agent any
    tools {
        maven "MAVEN3.9"
        jdk "JDK17"
    }
    
    environment {

        AVA_HOME = "/usr/lib/jvm/java-17-openjdk-amd64"  // Adjust this path to your JDK17 installation
        PATH = "${JAVA_HOME}/bin:${PATH}"
        SNAP_REPO = 'vprofile-snapshot'
		NEXUS_USER = 'admin'
		NEXUS_PASS = 'Sabir@92'
		RELEASE_REPO = 'vprofile-release'
		CENTRAL_REPO = 'vpro-maven-central'
		NEXUSIP = 'http://172.31.22.13'
		NEXUSPORT = '8081'
		NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'echo "JAVA_HOME is set to: $JAVA_HOME"'
                sh 'java -version'
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}