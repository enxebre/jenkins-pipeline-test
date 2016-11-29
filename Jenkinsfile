podTemplate(label: 'mypod', containers: [
	containerTemplate(name: 'jnlp', image: 'jenkinsci/jnlp-slave:2.52', args: '${computer.jnlpmac} ${computer.name}', command: ''),
    containerTemplate(name: 'docker', image: 'docker', ttyEnabled: true, command: 'cat'),
    containerTemplate(name: 'golang', image: 'golang:1.6.3-alpine', ttyEnabled: true, command: 'cat')
  ]) {

    node ('mypod') {

    	stage 'Pre ls'
		sh "ls -aslch"

        container('docker') {
            stage 'Run docker'
            sh 'docker ps'
            sh "ls -aslch"
        }

        stage 'Get a Golang project'
        git url: 'https://github.com/hashicorp/terraform.git'
        container('golang') {
            stage 'Build a Go project'
            sh """
            mkdir -p /go/src/github.com/hashicorp
            ln -s `pwd` /go/src/github.com/hashicorp/terraform
            cd /go/src/github.com/hashicorp/terraform && make core-dev
            """
        }

    }
}