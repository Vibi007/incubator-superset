pipeline {
  agent any
  stages {
    stage('Dev') {
      steps {
        sh '''pip install -r requirements.txt
pip install -r requirements-dev.txt
pip install mysqlclient
pip install cryptography
pip install -e .
sudo apt-get install build-essential libssl-dev libffi-dev python3.5-dev python-pip libsasl2-dev libldap2-dev
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