podTemplate(
    label: "build-pod",
    containers: [
        // containerTemplate(name: 'jnlp', image: 'jenkinsci/jnlp-slave:alpine', args: '${computer.jnlpmac} ${computer.name}'),
        containerTemplate(name: 'golang', image: 'liflandgaming/build-slave:k8-docker', ttyEnabled: true, alwaysPullImage: true, command: 'cat', envVars: [
                containerEnvVar(key: 'DOCKER_REGISTRY', value: 'hub.do.optibet.ee')
            ]),
        containerTemplate(name: 'docker', image: 'docker', ttyEnabled: true, command: 'cat')
    ],
    volumes: [
        hostPathVolume(hostPath: '/var/run/docker.sock', mountPath: '/var/run/docker.sock')
    ]
) {
    node('build-pod') {
	sh "env | sort"
    }
}

