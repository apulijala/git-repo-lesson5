node("master") {
    
    stage('Fetch Source Code') {
        git  'https://github.com/apulijala/git-repo-lesson5'    
    }
    
    dir('Lesson5') {
        printMessage("Running Pipeline")
        
        stage("Testing") {
            sh 'python test_functions.py'
        }

        stage("Deploymnet") {
            
            if (env.BRANCH_NAME == 'master' ) {
                printMessage("Deploying the Master Branch")
            }else {
                printMessage("No Deployment configured for this branch")
            }
        }
    }
    
    printMessage("Pipeline Complete")
    
    
}

def printMessage(message) {
    echo "${message}"   
}

