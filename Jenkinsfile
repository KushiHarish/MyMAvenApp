pipeline { 
	agent any 
	tools{
		maven 'Maven'
}
stages { 
stage('Checkout') { 
steps { 
// Check out code from Git repository 
git url: 'https://github.com/yourusername/your-maven- 
project.git', branch: 'main' 
} 

} 
stage('Build') { 
steps { 
// Run Maven build 
sh 'mvn clean package' 
} 
} 
stage('Test') { 
steps { 
// Optionally, separate test execution if needed 
sh 'mvn test' 
} 
} 
stage('Run application') { 
steps { 
// Optionally, separate test execution if needed 
sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar' 
} 
}
} 
post { 
always { 
// Archive test reports 
junit '**/target/surefire-reports/*.xml' 
} 
success { 
echo 'Build and tests succeeded!' 
} 
failure { 
echo 'Build or tests failed.' 
} 
} 
}
