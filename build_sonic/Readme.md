# build docker image
docker build -f Dockerfile -t sonic-build-image:v1.0 .

# run container in daemon
docker run -it -d -v /projects/falcon:/falcon --privileged --name="sonic-build-env001" sonic-build-image:v1.0

# enter contariner
docker exec -it sonic-build-env001 bash
