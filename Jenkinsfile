pipeline{
 agent any
 environment {
    ANYPOINT = credentials('ANYPOINT')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml package deploy  -Dusername=just4saa -Dpassword=Mule12345! -Denvironment=Sandbox -DmuleDeploy'
 			}
 		}
 	}
 }

}
