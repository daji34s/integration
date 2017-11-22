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
        jiraComment(issueKey: 'INTBAJAU-1', body: 'ini info ')
      }
    }
  }
}