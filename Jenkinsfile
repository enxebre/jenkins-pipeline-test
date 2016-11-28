node {
    echo 'Hello from Pipeline'

	stage ('preparation') {

		sh "uname -r"
		sh "id"
		sh "wget http://storage.googleapis.com/kubernetes-helm/helm-v2.0.0-beta.1-linux-amd64.tar.gz -O /tmp/helm.tar.gz"
		sh "tar -C /tmp -xvzf /tmp/helm.tar.gz"
		sh "/tmp/linux-amd64/helm init"
		sh "/tmp/linux-amd64/helm list"

		sh "env | sort"
		sh "pwd"
		sh "ls -aslch"
	
	}
}
