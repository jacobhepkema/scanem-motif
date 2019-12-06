Bootstrap: docker
From: debian:testing

# Based on https://github.com/ddiez/meme/blob/master/Dockerfile

%labels
  Maintainer @jacobhepkema
  Version v0.2

%environment
  # Change MEME version if necessary
  VERSION=5.1.0
  
%post
  # Install prerequisites
  
  apt-get update && apt-get install -y --no-install-recommends apt-utils
  apt-get update
  apt-get install -y build-essential python python3 zlib1g-dev libopenmpi-dev openmpi-bin ssh libxml2 libxslt1.1 libxml2-dev libxslt1-dev ghostscript libxml-sax-expat-perl curl
  
  # Get meme suite
  curl http://meme-suite.org/meme-software/$VERSION/meme-$VERSION.tar.gz > /tmp/meme_$VERSION.tar.gz
  cd /tmp && tar xfzv meme_$VERSION.tar.gz && cd /tmp/meme-$VERSION 
  ./configure --prefix /opt && make && make install
  
  # Remove tar and dir that were used for installation
  rm /tmp/meme_$VERSION.tar.gz && rm -rf /tmp/meme_$VERSION
  
  # Remove prerequisites that were only essential for installation of meme suite
  apt-get purge -y build-essential zlib1g-dev libopenmpi-dev curl libxml2-dev libxslt1-dev && apt-get autoremove -y
  
  # Executables are in this folder, add to system env PATH
  export PATH=/opt/bin:$PATH
  
# smoke test
meme -version

%runscript
  exec /bin/bash "$@"
