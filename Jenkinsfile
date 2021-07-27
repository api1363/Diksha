pipeline {
    agent any
    stages {
        stage('one') {
            steps {
               echo 'this is one'
            }
        }
        stage('two') {
            steps {
                input('this is two')
            }
        }
        stage('three') {
            when{
                not {
                    branch "master"
                }
            }
            steps{
                echo "hello"
        }
        stage('four') {
            parallel{
                stage('unit test'){
                    steps {
                         echo "this is four"
                    }
                   }
                stage('integration test'){
                    agent{
                        docker{
                            reuseNode false
                            image 'ubantu'}
                    }
                    steps{
                        echo 'this is done'
                    }
                }
            }
        }
        }
    }
}
             
