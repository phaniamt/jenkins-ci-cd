# jenkins-ci-cd


    kubectl get namespaces

    kubectl apply -f jenkins-namespace.yaml

    kubectl get namespaces --show-labels

    kubectl config view

    kubectl config current-context

    kubectl config set-context dev --namespace=dev --cluster=phani-cluster.us-east-1.eksctl.io --user=eks-uesr@phani-cluster.us-east-1.eksctl.io

    kubectl config use-context dev

    kubectl config current-context


# if you face docker build host reslove issue login into EC2 enable the docker bridge otherwise follow the docker-deamon-bridge-enable.yaml add the bootstrap commands while creating the nodes

# Ref 

https://gist.github.com/tobemedia/2144d74d232ccce8972613e8ae13b054

vi /etc/docker/daemon.json

        {
          "bridge": "docker0",
          "log-driver": "json-file",
          "log-opts": {
            "max-size": "10m",
            "max-file": "10"
          },
          "live-restore": false,
          "max-concurrent-downloads": 10
        }
        
service docker restart

systemctl daemon-reload
