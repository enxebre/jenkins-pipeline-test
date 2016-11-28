node {
    echo 'Hello from Pipeline'

	stage ('preparation') {

		sh "wget http://storage.googleapis.com/kubernetes-helm/helm-v2.0.0-beta.1-linux-amd64.tar.gz -O /tmp/helm.tar.gz"
		sh "tar -C /tmp -xvzf /tmp/helm.tar.gz"
		sh "cp /tmp/linux-amd64/helm /usr/local/linux-amd64/helm"

		sh "env | sort"

		sh "mkdir -p ${workDir}"
		sh "cp -R ${pwd}/* ${workDir}"
	
	}
}
