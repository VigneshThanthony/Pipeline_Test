pipeline { 
    agent any 

    stages
    {
        stage ('Build')
        {
            steps
            {
                echo 'Build App'
                build 'first_job'
            }
        }
        
        stage ('Test')
        {
            steps
            {
                echo 'Test App'
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
