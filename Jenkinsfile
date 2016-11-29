#!/usr/bin/groovy
@Library('github.com/docker/jenkins-pipeline-scripts@master')

def utils = new io.fabric8.Utils()

node {

	def envStage = utils.environmentNamespace('staging')


	stage ('preparation') {

		sh "uname -r"
		sh "id"
		sh "wget https://kubernetes-helm.storage.googleapis.com/helm-v2.0.0-linux-amd64.tar.gz -O /tmp/helm.tar.gz"

		sh "tar -C /tmp -xvzf /tmp/helm.tar.gz"
		sh "/tmp/linux-amd64/helm init"
		sh "/tmp/linux-amd64/helm list"

		sh "env | sort"
		sh "pwd"
		sh "ls -aslch"
		sh "java -version"
	}
}
