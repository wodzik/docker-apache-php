FROM droptica/apache-php:xdebug-php5

RUN pecl d xhprof-0.9.4 \
    && tar xzf xhprof-0.9.4.tgz \
    && mv xhprof-0.9.4 xhprof \
    && rm xhprof-0.9.4.tgz \
    && mv xhprof /opt/ \
    && cd /opt/xhprof/extension \
    && phpize \
    && ./configure --enable-xhprof \
    && make \
    && make install

ADD xhprof.ini /usr/local/etc/php/conf.d/xhprof.ini
