podTemplate(
    label: 'mypod', 
    inheritFrom: 'default',
    containers: [
        containerTemplate(
            name: 'ubuntu', 
            image: 'latest',
            ttyEnabled: true,
            command: 'cat'
        )
    ]
) {
    node('mypod') {
        def commitId
        stage ('Checkout repo') {
            checkout scm
        }
        stage ('List repo in another container') {
            container ('ubuntu') {
                sh 'ls'
                sh 'find / -name jenkins-tests'
            }
        }
    }
}