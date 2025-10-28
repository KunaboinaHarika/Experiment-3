pileline{
agent any
tools{
maven'maven'
jdk'jenkins'
}
stages{
stage('chesckout'){
steps{
gitbranch:'master',
url:'git@gitbub.com:codefeeding99/
test and build_using_pipe_line.git',
credentials Id:'pipeline_key'
}
}
stage('build'){
steps{
bat'mvn clean install'
}
}
stage('run tests'){
steps{
bat'mvn test'
}
}
stage('package'){
steps{
bat'mvn package'
}
}
stage('deployment(optimal)'){
steps{
echo"deployement stage"
}
}
}
post{
success{
echo"pipeline completed successfully!"
}
}
failure{
echo"build or test failure check logs above'
}
}
}


