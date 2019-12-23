# Datei Dockerfile
FROM nodered/node-red:latest

LABEL maintaner "norbert.schlemmer@neunzehn.at"

USER root
RUN echo "Europe/Vienna" > /etc/timezone
# RUN dpkg-reconfigure -f noninteractive tzdata

RUN npm install --save node-red-dashboard node-red-contrib-influxdb node-red-contrib-modbus

RUN npm install --save codmpm/node-red-contrib-loxone

WORKDIR /usr/src/node-red

USER node-red

# User configuration directory volume
VOLUME ["/data"]
EXPOSE 1880

# Environment variable holding file path for flows configuration
ENV FLOWS=flows.json

CMD ["npm", "start", "--", "--userDir", "/data"]
