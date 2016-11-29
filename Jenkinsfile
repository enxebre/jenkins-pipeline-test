podTemplate(label: 'mypod', containers: [
	containerTemplate(name: 'jnlp', image: 'jenkinsci/jnlp-slave:2.52', args: '${computer.jnlpmac} ${computer.name}', command: ''),
    containerTemplate(name: 'docker', image: 'docker:1.11.2', ttyEnabled: true, command: 'cat'),
  ],
  volumes: [hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock')]) {

    node ('mypod') {

    	stage 'Run inside default node.'
		sh "pwd"
		sh "touch lolailo-file"
		sh "ls -aslch"

        container('docker') {
            stage 'Run docker'
            sh 'docker ps'
            sh "ls -aslch"
        }
    }
}