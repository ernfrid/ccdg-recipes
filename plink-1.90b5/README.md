# production mode

    docker build -t plink-1.90b5:v1 .
    docker run -i -t -v $PWD:/release --rm plink-1.90b5:v1

# Development Mode

comment out the "COPY" commands in the Dockerfile, and then run:

    docker build -t plink-1.90b5:v1 .
    docker run -i -t -v $PWD:/build --rm plink-1.90b5:v1 bash

# Testing

    docker build -t plink-1.90b5:v1 .
    docker run -i -t -v $PWD:/release --rm plink-1.90b5:v1 bash

    # inside the container
    cd /release
    # manually install the prerequisites for the package
    apt-get install libc6 zlib1g libstdc++6 libgcc1 libblas3 liblapack3 libgfortran3 libatlas3-base
    dpkg --install ccdg-plink-1.90b5_1.90b5-1ubuntu14.04.deb
