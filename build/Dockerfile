FROM alpine:3.12
RUN apk update && \ 
    apk add --no-cache --allow-untrusted -f --clean-protected -u -l -q -v vsftpd && \
    wait && \
    rm -rf /var/cache/apk/* 
COPY start_vsftpd.sh /bin/start_vsftpd.sh
COPY vsftpd.conf /etc/vsftpd/vsftpd.conf
EXPOSE 21 21000-21010
VOLUME /ftp
ENTRYPOINT ["/bin/start_vsftpd.sh"]