# sudo docker build --rm --no-cache -t myalpine:latest .
# sudo docker run --rm -p 2222:22 -d --name=myalpine1 --hostname=myalpine1 myalpine:latest

FROM alpine:3
ENTRYPOINT ["/entrypoint.sh"]
#EXPOSE 22
COPY rootfs /

RUN apk add --no-cache openssh doas alpine-conf open-rc \
  && adduser -D admin && echo -e "admin\nadmin" | passwd admin \
  && echo "permit nopass admin as root" > /etc/doas.d/doas.conf 
