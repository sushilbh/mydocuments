node('maven'){
    def mvnhome = tool name: 'mvn360', type: 'maven'
    stage('checkout'){
        echo "clonning the respoos"
    }
   
    stage('package'){
        echo "package"
        sh "$mvnhome/bin/mvn clean test surefire-report:report-only"
        junit allowEmptyResults: true, testResults: '/pipeline/target/*.jar'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site', reportFiles: 'surefire-report.html', reportName: 'surefire-reports.html', reportTitles: ''])
        archiveArtifacts 'target/**/*'
        
    }
     stage('maven'){
        echo "test"
        sh "$mvnhome/bin/mvn clean package -DskipTests=true"
    }
}
