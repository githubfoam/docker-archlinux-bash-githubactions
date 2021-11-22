FROM ubuntu:21.04    
LABEL org.opencontainers.image.authors="githubfoam"

RUN apt-get update -qy && apt-get -yq dist-upgrade &&\
    # Uninstall unattended-upgrades
    apt-get purge unattended-upgrades &&\ 
    # Enable retry logic for apt up to 11 times
    echo "APT::Acquire::Retries \"11\";" > /etc/apt/apt.conf.d/80-retries &&\
    # Configure apt to always assume Y
    echo "APT::Get::Assume-Yes \"true\";" > /etc/apt/apt.conf.d/90assumeyes &&\
    echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections &&\
    apt-get install -qy --no-install-recommends apache2 

