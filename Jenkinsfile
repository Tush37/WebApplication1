//def ReleaseDir = "c:\inetpub\wwwroot"
pipeline {
			agent any
			stages {
				stage('Source'){
					steps{
						checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '0f478fd8-a8d0-46db-871c-754f23532d55', url: 'https://github.com/Tush37/WebApplication1.git']]])
					}
				}
				stage('Build') {
    					steps {
						 bat "\"${tool 'MSBuild14'}\" WebApplication1.sln /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\inetpub\\wwwroot"
    					}
					}
				}
			}
}
