stage "DEV-QA"

node {
	// all pipeline code runs on a node
	
	// clone a Git Repo
	git 'https://github.com/ajscilingo/se441-qotd-pipeline.git'
	
	//access gradle from jenkins config
	def gradleHome = tool 'Gradle 2.12'
	sh "${gradleHome}/bin/gradle assemble uploadArchives"
	
	step([$class: 'ArtifactArchiver', artifacts: '**/*.war',
	fingerprint: true])
 }
