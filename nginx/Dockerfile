FROM nginx:1.21.3
RUN touch /etc/nginx/conf.d/app.conf
CMD /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
#COPY ./nginx/index.html /usr/share/nginx/html
#CMD /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
EXPOSE 8080