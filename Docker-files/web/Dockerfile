FROM nginx
LABEL "project"="Vprofile"
LABEL "Author"="ssb"

#Remove existing default configuration file in nginx
RUN rm -rf /etc/nginx/conf.d/default.conf 
COPY nginvproapp.conf /etc/nginx/conf.d/vpconfig.conf