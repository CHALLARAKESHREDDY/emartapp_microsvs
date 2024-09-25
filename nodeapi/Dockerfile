FROM nodejs:14 AS NODE_IMAGE
WORKDIR /usr/src/app/
COPY ./ ./nodeapi/
RUN  cd nodeapi && npm install

FROM nodejs:14
WORKDIR /usr/src/app/
COPY --from=NODE_IMAGE /usr/src/app/nodeapi/ ./
RUN ls
EXPOSE 5000
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm start"]
