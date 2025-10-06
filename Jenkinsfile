// NOTE: Requires Pipeline Utility Steps and HTTP Request Plugin 
import groovy.json.JsonSlurperClassic

pipeline {
    agent any
    stages {
        stage('Data') {
            steps {
                script {
                    def str = 
                            '''
                            {
                            "users": [
                                {"id": 1, "profile": {"username": "alice"}},
                                {"id": 2, "profile": {"username": "bob"}},
                                {"id": 3, "profile": {"username": "alice"}}
                            ]
                            }
                            '''
                            def obj = new JsonSlurperClassic().parseText(str)
                            println obj
                            def res = []
                            obj.users.each{ ch ->
                            def n = ch.profile.username
                            if(!res.contains(n)){
                                res << n
                            }
                            }
                            println res

                    // echo 'API call'
                    // def api = req(
                    //     url: //URL , 
                    //     mode:'GET',
                    //     resp: 'BODY'
                    // )
                    // def str = api.content
                    // echo "API Response JSON: ${str}"
                    // def parsedJson = readJSON(text: str) //readJSON from pipeline utility plugin
                    // echo "parsed json is ${parsedJson}"
                }
            }
        }
    }
}
