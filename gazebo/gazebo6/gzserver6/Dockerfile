# This is an auto generated Dockerfile for gazebo:gzserver6
# generated from templates/docker_images/create_gzserver_image.Dockerfile.em
# generated on 2015-08-19 15:31:14 -0400
FROM ubuntu:trusty
MAINTAINER Nate Koenig nkoenig@osrfoundation.org

# setup keys
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys D2486D2DD83DB69272AFE98867170598AF249743

# setup sources.list
RUN echo "deb http://packages.osrfoundation.org/gazebo/ubuntu `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-latest.list

# install gazebo packages
RUN apt-get update && apt-get install -q -y \
    gazebo6=6.1.0* \
    && rm -rf /var/lib/apt/lists/*

# setup environment
EXPOSE 11345

# setup entrypoint
COPY ./gzserver_entrypoint.sh /

ENTRYPOINT ["/gzserver_entrypoint.sh"]
CMD ["gzserver"]
