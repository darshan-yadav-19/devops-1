pipeline{
    
    agent any

    stages {
       
           stage ("clone"){
        steps {
            checkout scm 
        }
       }
       
       stage ("build"){

        steps {
           sh 'mkdir -p 12345'
           sh 'ls'
        }
       }

  

       stage ("deploy"){
        steps {
            echo "Good TO SEE YOU"
        }
       }
    }
    post {                        // ← NEW: Add this block
        success {
            echo "✅ Pipeline finished successfully!"
        }
        failure {
            echo "❌ Something went wrong!"
        }
    }
}
