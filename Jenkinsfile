node {
  try {
    stage ('Clone') {
      checkout scm
    }
    stage ('Build') {
      sh "echo 'shell scripts to build project...'"
      sh "echo 'Running ${env.BRANCH_NAME}'"
    }
    stage ('Tests') {
    }
  } catch (err) {
    currentBuild.result = 'FAILED'
      throw err
  }
}
