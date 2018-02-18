pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
	            sh 'make test_xunit || true'
              step([$class: 'XUnitBuilder',
              tresholds: [
                [$class: 'SkippedThreshold', failureThreshold: '0'],
                [$class: 'FailedThreshold', failureThreshold: '1']],
              tools: [[$class: 'JUnitType', pattern: 'test_results.xml']]])
        	}
        }
    }
}
