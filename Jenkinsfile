pipeline{

    agent any

//     environment{
//
//             MYSQL_DATABASE: 'spring-security-rbac'
//             MYSQL_USER: 'sa'
//             MYSQL_PASSWORD: 'password'
//             MYSQL_ROOT_PASSWORD: 'password'
//
//     }



    stages{

//        stage("verify tooling"){
//             steps {
//               sh '''
//
//               docker compose version
//
//               '''
//             }
//        }

    stage('Prune Docker data') {
      steps {
        bat 'docker system prune -a --volumes -f'
      }
    }

    stage('Start container') {
      steps {
        bat 'docker compose up -d --no-color --wait'
        bat 'docker compose ps'
      }
    }


      stage("deploy"){
        steps {
          echo 'deploying the application...'
        }
      }

//
//     post {
//       always {
//         sh 'docker compose down --remove-orphans -v'
//         sh 'docker compose ps'
//       }
//     }

  }


}