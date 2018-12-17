pipeline {
  agent any
  stages {
    stage('Dev') {
      steps {
        sh '''python3 -m venv Superset_jenkins
cd Superset_jenkins
source bin/activate
pip install -r requirements.txt'''
      }
    }
  }
}