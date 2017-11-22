pipeline {
  agent none
  stages {
    stage('Development') {
      parallel {
        stage('Development') {
          steps {
            echo 'hello world'
          }
        }
        stage('trigger commit') {
          steps {
            acceptGitLabMR(mergeCommitMessage: 'commit')
          }
        }
      }
    }
    stage('send issue to Jira') {
      steps {
        jiraNewIssue(issue: 'testing', auditLog: true, failOnError: true, site: '192.168.99.100:32768')
      }
    }
  }
}