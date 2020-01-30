# Datei Dockerfile
# FROM nodered/node-red:latest
FROM nodered/node-red:latest-12-minimal

LABEL maintaner "norbert.schlemmer@neunzehn.at"

USER root
RUN echo "Europe/Vienna" > /etc/timezone
# RUN dpkg-reconfigure -f noninteractive tzdata

RUN npm install --unsafe-perm node-red-dashboard node-red-contrib-influxdb node-red-contrib-modbus

RUN npm install --unsafe-perm node-red-contrib-loxone
RUN npm install --unsafe-perm node-red-contrib-cpu node-red-contrib-ccu

WORKDIR /usr/src/node-red

USER node-red

# User configuration directory volume
VOLUME ["/data"]
EXPOSE 1880

# Environment variable holding file path for flows configuration
ENV FLOWS=flows.json

CMD ["npm", "start", "--", "--userDir", "/data"]
