@Library([
    'continuous-deployment-library@master', 
    'shared-library@improvement/retrieve-shared-library-at-runtime-instead-of-env-variable'
]) _


node('master') {

    dir( "${WORKSPACE}@shared-library") {
        //This is the path library.
        //Run any command to get branch name
        //git show -s --pretty=%D HEAD | tr -s ',' '\n' | sed 's/^ //' | grep -v -e HEAD -e '^origin/' | head -n1
        sh "pwd"
        sh "ls -l .."
        sh "git branch -a"
        def branch = sh script: "git show -s --pretty=%D HEAD | tr -s ',' '\n' | sed 's/^ //' | grep -v -e HEAD -e '^origin/'", returnStdout: true

        echo "hello god"
        echo "Branch: '$branch'"
    }
}


/*
env.PIPELINE_BRANCH = "feature/create-networks-during-docker-deploy"
continuousDeployment()
*/