stage('Checkout') {
    node {
        git 'https://github.com/martinpbarber/jenkins'   
    }
}

stage('Push to S3') {
    echo "Pushing to S3"
    node {
        step([$class: 'S3BucketPublisher', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'cloudformation-jenkins', excludedFile: 'Jenkinsfile,README.md', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-west-2', showDirectlyInBrowser: false, sourceFile: '*', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], profileName: 'CloudFormation S3', userMetadata: []])
    }
}
