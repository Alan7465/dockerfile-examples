#!/usr/bin/env groovy

node ('dockerserver') {
        stage "build"
        checkout scm
        def customImage = docker.build("docker-image:${env.BUILD_ID}", "-f ./apache/Dockerfile .")
        
        stage "test copying files"
        customImage.withRun('-v $PWD:/app -u root') {
            /* Run some tests which require MySQL */
            sh 'ls /app && touch /app/test.html && ls /app' // can see that test.html is generated
        }
}
