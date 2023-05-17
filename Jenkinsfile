pipeline { 
    agent any 

    stages
    {
        stage ('Build')
        {
            steps
            {
                build 'second-job'
            }
        }
        
        stage ('Test')
        {
            steps
            {
                test 'third-job'
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
