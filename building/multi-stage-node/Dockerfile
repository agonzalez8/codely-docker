# This stage installs our modules
FROM mhart/alpine-node:12
RUN mkdir app
WORKDIR app
COPY ./app/package.json  .

RUN npm install

# Then we copy over the modules from above onto a `slim` image
FROM mhart/alpine-node:slim-12
RUN mkdir app
WORKDIR app
COPY --from=0 ./app .
COPY ./app .
CMD ["node", "index.js"]
