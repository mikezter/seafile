Readme-Debian
===

This information aims to help setup a Debian development box for Seafile.

Debian packages
---

These packages are required:

    sudo apt-get install \
      git-core \
      automake \
      autoconf \
      libtool \
      intltool \
      libglib2.0 \
      uuid-dev \
      libevent-dev \
      libsqlite3-dev \
      libssl-dev

These packages are dependencies of the GUI client:

    sudo apt-get install \
      libgtk+2.0-dev \
      libnotify-dev

This package is a dependency of Libzdb:

    sudo apt-get install flex

Vendored dependencies
---

Install Jansson:

    git clone git@github.com:akheron/jansson.git && cd jansson &&\
      autoreconf -i &&\
      ./configure && make && sudo make install

Install Libsearpc:

    git clone git@github.com:haiwen/libsearpc.git && cd libsearpc &&\
      automake --add-missing --copy &&\
      ./autogen.sh && ./configure && make && sudo make install

Install Libzdb:

    wget http://www.tildeslash.com/libzdb/dist/libzdb-2.12.tar.gz &&\
      tar xzvf libzdb-2.12.tar.gz && cd libzdb-2.12 &&\
      autoconf && ./configure && make && sudo make install

Install Ccnet:

    git clone git@github.com:haiwen/ccnet.git && cd ccnet &&\
      ./autogen.sh && ./configure --enable-server && make && sudo make install

Install Seafile:

    automake --add-missing --copy

Now proceed according to README.
