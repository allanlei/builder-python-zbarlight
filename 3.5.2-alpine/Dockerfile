FROM        python:3.5.2-alpine

ENV         LIBRARY_PATH /lib:/usr/lib
RUN         apk --no-cache add --virtual .builddeps \
                build-base \
                binutils \
                git \
                autoconf \
                libtool \
                automake \
                gettext-dev \
                freetype-dev \
                fontconfig-dev \
                imagemagick-dev \
                lcms2-dev \
                zlib-dev \
                xmlto \
                v4l-utils-dev \
                linux-headers && \
            git clone https://github.com/allanlei/ZBar.git && \
            cd ZBar && \
            autoreconf -vif && \
            ./configure --prefix=/usr --without-gtk --without-java --without-qt --without-python && \
            make && \
            make install && \
            pip install zbarlight && \
            apk del .builddeps && \
            rm -rf ZBar
# RUN         python setup.py bdist_wheel
