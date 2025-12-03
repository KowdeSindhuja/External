pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Build a docker image"
                bat "docker build -t mypythonapp ."
            }
        }
        stage("Run") {
            steps {
                echo "Run docker Image"
                bat "docker rm -f mycontainer || exit 0"
                bat "docker run -d -p 5000:5000 --name mycontainer mypythonapp"
            }
        }
    }
    post {
        success {
            echo "pipeline successful"
        }
        failure {
            echo "pipeline failure"
        }
    }
}
