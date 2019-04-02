node('maven'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    echo "downloading scm"
    stage('checkout'){
        git credentialsId: 'githubacc', url: 'https://github.com/ramharig/simple-java-maven-app.git'
    }
    stage('test'){
        echo "executing test cases"
        sh "${mvnHome}/bin/mvn clean test surefire-report:report-only"
        archiveArtifacts 'target/surefire-reports/*'
        junit 'target/surefire-reports/*.xml'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/', reportFiles: 'surefire-report.html', reportName: 'HTMLReport', reportTitles: ''])
    }
    stage ('build'){
        echo "build the package"
        sh "${mvnHome}/bin/mvn package -DskipTests=true"
    }
    stage('postbuild action'){
        echo "send email notification to the user"
    }
    stage('email for approval'){
        timeout(30) {
        input message: 'Do you want to proceed?' , ok: 'Deploy'
        sh "mutt -s 'the file is ready Please review' ghimire.1987@gmail.com"
    }
    }
        // timeout(time: 30, unit: 'MINUTES') 
        // input message: 'Do you want to proceed?' , ok: 'Deploy'

    stage('backing up to s3'){
    withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-secrect-key', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
     sh "aws s3 cp target/my-app-1-RELEASE.jar s3://ghimire-bucket/"  
    } 
    }
    stage('deploy to target'){
    sshagent(['target-key']) {
    sh "scp -o StrictHostKeyChecking=no target/my-app-1-RELEASE.jar ec2-user@54.242.240.0:/home/ec2-user"
    }
}
}
