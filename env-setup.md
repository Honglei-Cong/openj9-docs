
### Prepare your system

Save the Dockerfile to your current directory and specify these commands to build and run the Docker image:

```
docker build -t openj9 -f Dockerfile .
docker run -it openj9
```


### Get the source

This repository is a git mirror of OpenJDK without the HotSpot JVM, but with an openj9 branch that contains a few necessary patches. Run the following command:

```
git clone https://github.com/ibmruntimes/openj9-openjdk-jdk8
cd openj9-openjdk-jdk8
bash ./get_source.sh

```


### Configure

You must specify one extra jar file, which has already been installed into the Docker container.

```
bash ./configure --with-freemarker-jar=/root/freemarker.jar
```


### Build

```
make images
```

