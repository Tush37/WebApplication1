//def ReleaseDir = "c:\inetpub\wwwroot"
pipeline {
			agent any
			stages {
				stage('Source'){
					steps{
						git 'https://github.com/Tush37/WebApplication1.git'
				}
				stage('Build') {
    					steps {
    					    bat "\"${tool 'MSBuild'}\" WebApplication1.sln /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\inetpub\\wwwroot"
    					}
				}
			}
}
}
