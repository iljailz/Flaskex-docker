node ('docker'){


    withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
    // some block

    stage ("Build"){
    checkout scm

    sh """
        docker build -t iljailz/flaskex2 .
    """
    }
    stage ("Push image"){
        sh """
        docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD
        docker push iljailz/flaskex2
        """

    }
    }
}
