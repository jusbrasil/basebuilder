# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru spark image
# to run it:
# 1- run: $ tsuru-admin platform-add spark -d https://raw.github.com/jusbrasil/basebuilder/master/spark/Dockerfile

from	ubuntu:14.04
run     locale-gen en_US.UTF-8
env     LANG=en_US.UTF-8 LANGUAGE=en_US:en LC_ALL=en_US.UTF-8
run	apt-get update
run	apt-get install wget -y --force-yes
run	wget http://github.com/jusbrasil/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run	mkdir /var/lib/tsuru
run	tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run	rm basebuilder.tar.gz
run	cp /var/lib/tsuru/java/deploy /var/lib/tsuru
run	cp /var/lib/tsuru/java/start /var/lib/tsuru
run	/var/lib/tsuru/java/install
run /var/lib/tsuru/spark/install 
env SPARK_HOME /opt/spark
env MESOS_NATIVE_JAVA_LIBRARY /usr/local/lib/libmesos.so
