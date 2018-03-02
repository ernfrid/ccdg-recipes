# production mode

    docker build -t king-2.1.3:v1 .
    docker run -i -t -v $PWD:/release --rm king-2.1.3:v1

# Development Mode

comment out the "COPY" commands in the Dockerfile, and then run:

    docker build -t king-2.1.3:v1 .
    docker run -i -t -v $PWD:/build --rm king-2.1.3:v1 bash

# Testing

    docker build -t king-2.1.3:v1 .
    docker run -i -t -v $PWD:/release --rm king-2.1.3:v1 bash

    # inside the container
    cd /release
    # manually install the prerequisites for the package
    apt-get install libc6 zlib1g libgomp1 libstdc++6 libgcc1
    dpkg --install ccdg-king-2.1.3_2.1.3-1ubuntu14.04.deb
