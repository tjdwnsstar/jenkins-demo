pipeline {
    agent any
    
    stages {
        stage('환경 확인') {
            steps {
                echo '=== 환경 확인 단계 ==='
                sh 'node --version'
                sh 'npm --version'
            }
        }
        
        stage('체크아웃') {
            steps {
                echo '=== Git 소스코드 체크아웃 ==='
                checkout scm
            }
        }
        
        stage('의존성 설치') {
            steps {
                echo '=== NPM 패키지 설치 ==='
                sh 'npm install'
            }
        }
        
        stage('테스트') {
            steps {
                echo '=== 테스트 실행 ==='
                sh 'npm test'
            }
        }
        
        stage('빌드') {
            steps {
                echo '=== 애플리케이션 빌드 ==='
                sh 'echo "빌드 완료!"'
            }
        }
        
        stage('배포 준비') {
            steps {
                echo '=== 배포 준비 완료 ==='
                sh 'echo "배포 가능한 상태입니다!"'
            }
        }
    }
    
    post {
        success {
            echo '✅ 파이프라인이 성공적으로 완료되었습니다!'
        }
        failure {
            echo '❌ 파이프라인이 실패했습니다!'
        }
        always {
            echo '🔄 파이프라인 실행이 종료되었습니다.'
        }
    }
}
