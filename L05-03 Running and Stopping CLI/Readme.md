Docker CLI cheatsheet running and stopping

docker pull [imageName]                 Pull an image from a registry
docker run [imageName]                  Run containers
docker run -d [imageName]               Detached mode
docker start [containerName]            Start stopped containers
docker ps                               List running container
docker ps -a                            List running and stopped container
docker stop [containerName]             Stop container
docker kill [containerName]             Kill container
docker image inspect [imageName]        Get image info


Docker Limits

docker run --memory="256m" nginx        Max Memory
docker run --cpus=".5" nginx            Max CPU