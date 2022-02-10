Only tested in Debian 11

# Build commands

```shell
apt -y install build-essential libatomic-ops-dev libsctp-dev
./configure --prefix=/usr/local \
--conf-path=/etc/nginx/nginx.conf \
--error-log-path=/var/log/nginx.log \
--pid-path=/var/run/nginx.pid \
--lock-path=/var/run/nginx.lock \
--with-openssl-opt="enable-ec_nistp_64_gcc_128 threads zlib sctp" \
--with-stream --with-stream_ssl_module \
--with-stream_realip_module --with-stream_ssl_preread_module \
--with-http_ssl_module --with-http_v2_module --with-http_realip_module --with-http_addition_module --with-http_sub_module  --with-http_degradation_module --with-http_slice_module  --with-pcre --with-libatomic --with-compat --with-file-aio --with-threads --with-poll_module --with-select_module --with-openssl=./openssl-3.0.1 --with-cc-opt="-static -s" --with-ld-opt="-static -lcrypt" --with-pcre=./pcre-8.45 --with-zlib=./zlib-1.2.11
```

# Use nginx for relay

```shell
./nginx -c $(pwd)/conf
```
