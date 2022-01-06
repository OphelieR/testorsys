pipeline {
  agent any
  stages {
    stage('first stage') {
      steps {
        sh 'grep user /etc/passwd'
      }
    }

    stage('second stage') {
      steps {
        sh '''if test `grep -c orsys /etc/passwd` -ne 0
then 
find / -user orsys  > /tmp/orsys
fi'''
      }
    }

    stage('thirs stage') {
      steps {
        sh '''for i in `cat /tmp/orsys`
do
ls -il $i
done'''
      }
    }

  }
}