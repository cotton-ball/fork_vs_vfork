node {
def app
stage('Clone repository') {
git 'https://github.com/cotton-ball/fork_vs_vfork.git'
}
stage('Build image') {
app = docker.build("nnnnn9915/test")
}
stage('Test image') {
app.inside {
sh 'make test'
}
}
stage('Push image') {
docker.withRegistry('https://hub.docker.com/repository/docker/nnnnn9915/test', 'nnnnn9915') {
app.push("${env.BUILD_NUMBER}")
app.push("latest")
}
}
}
