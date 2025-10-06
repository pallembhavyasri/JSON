// NOTE: Requires Pipeline Utility Steps and HTTP Request Plugin 
pipeline {
    agent any
    stages {
        stage('Data') {
            steps {
                script {
                    echo 'API call'
                    def api = req(
                        url: //URL , 
                        mode: 'GET',
                        resp: 'BODY'
                    )
                    def str = api.content
                    echo "API Response JSON: ${str}"
                    def parsedJson = readJSON(text: str) //readJSON from pipeline utility plugin
                    echo "parsed json is ${parsedJson}"
                }
            }
        }
    }
}
