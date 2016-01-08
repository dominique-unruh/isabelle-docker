FROM ubuntu

# Installing prerequisites
RUN apt-get -y update
RUN apt-get install -y lib32stdc++6 openjdk-7-jre wget ed libgomp1

# Downloading and installing Isabelle
RUN wget https://isabelle.in.tum.de/dist/Isabelle2015_linux.tar.gz -O /tmp/Isabelle.tar.gz
RUN cd /opt && tar xf /tmp/Isabelle.tar.gz
RUN rm /tmp/Isabelle.tar.gz
RUN /opt/Isabelle2015/bin/isabelle install /usr/bin

# Create a user "user" and data directory (for mounting the host)
RUN useradd -m user && adduser user sudo && (echo user:user | chpasswd) && (echo root:root | chpasswd)
RUN mkdir /home/user/data && chown user /home/user/data
WORKDIR /home/user/data

# Installing script for building heaps
ADD build-heap /root/build-heap
