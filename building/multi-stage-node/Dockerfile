# This stage installs our modules
FROM mhart/alpine-node:12
RUN mkdir app
WORKDIR app
COPY ./app/package.json  .

RUN npm install

# Then we copy over the modules from above onto a `slim` image
FROM mhart/alpine-node:slim-12

COPY --from=0 . .
COPY . .
WORKDIR app
CMD ["node", "index.js"]
