pipeline { 
    agent any 

    stages
    {
        stage ('Build')
        {
            steps
            {
                echo 'second-job'
                
            }
        }
        
        stage ('Test')
        {
            steps
            {
                echo 'third-job'
            }
        }
        
        stage ('Deploy')
        {
            steps
            {
                echo 'Deploy App'
            }
        }
    }
}
