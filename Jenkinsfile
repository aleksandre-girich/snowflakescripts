pipeline {
    agent {
        docker {
            image "python:3.8"
            args '--user 0:0'
        }

    }
    stages {
        stage('Run schemachange') {
            steps {
                sh "pip install schemachange --upgrade"
                sh "schemachange -f migrations -a hq72588.us-east-2.aws -u Aaleksandreg -r spokdeveloper -w SPOK_WH -d CORE_DWH -c CORE_DWH.SCHEMACHANGE.CHANGE_HISTORY --create-change-history-table"
            }
        }
    }
}
tetst