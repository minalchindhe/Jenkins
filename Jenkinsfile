node {
  try {
    stage ('Clone') {
      checkout scm
    }
    stage ('Build') {
        sh gem install bundler
        sh bundle install
        //sh cp config/database-gitlab.yml config/database.yml
        sh bundle exec rake db:create db:migrate RAILS_ENV=test
        sh bundle exec rake test
        ....
    }
    stage ('Build1') {
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
