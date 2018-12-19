pipeline {
  agent any
  stages {
    stage('Dev') {
      steps {
        sh '''pip install -r requirements.txt
pip install -r requirements-dev.txt
pip install -e .
superset db upgrade
superset init
cd superset
FLASK_ENV=development flask run -p 8089 --with-threads --reload --debugger
npm install -g yarn
cd superset/assets
yarn install
npm run dev-server -- --supersetPort=8089'''
      }
    }
  }
}