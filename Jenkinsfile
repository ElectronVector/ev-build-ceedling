pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'ceedling test:all'
            }
            post {
                  always {
                        xunit tools: [Custom(customXSL: 'unity.xsl',
                            pattern: 'build/artifacts/test/report.xml',
                            skipNoTestFiles: false,
                            stopProcessingIfError: true)]
                  }
             }
        }
    }
}