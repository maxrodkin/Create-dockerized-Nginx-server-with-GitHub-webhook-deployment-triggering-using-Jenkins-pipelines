node {
        stage("build") {
        // Clean up workspace
        step([$class: 'WsCleanup'])
        sh "docker build -t maxi4/maxrodkin:for_aws_1 github.com/maxrodkin/ms-docker-nginx-lua"
        //sh "docker run -d -p 8001:80 maxrodkin:for_aws_1"
        sh "docker login -u maxi4 -p P@ssw0rd_4"
        sh "docker push maxi4/maxrodkin:for_aws_1"
        sh "docker-machine create --driver amazonec2 --amazonec2-region eu-west-1 --amazonec2-vpc-id vpc-6440e402 --amazonec2-access-key AKIAJMJNZJHEYQICHZNA --amazonec2-secret-key 
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 aws-mr-nginx-lua-6"
        sh "docker-machine env aws-mr-nginx-lua-6"
        sh "eval \$(docker-machine env aws-mr-nginx-lua-6)"
        sh "docker run -d -p 80:80 maxi4/maxrodkin:for_aws_1"
        // Clean up workspace
        step([$class: 'WsCleanup'])
        }
    
    }
