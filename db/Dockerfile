FROM redis
COPY redis.conf /usr/local/etc/redis/redis.conf
RUN chown redis:redis /usr/local/etc/redis/redis.conf
EXPOSE 6379
VOLUME /data
CMD [ "/usr/local/etc/redis/redis.conf" ]
