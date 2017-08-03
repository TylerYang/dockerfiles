FROM elaijuh/node:latest
ENV PROJECT_NAME json-server
MAINTAINER tyleryang <tyler.z.yang@gmail.com>

RUN mkdir /app
WORKDIR /app

RUN yarn global add json-server faker

EXPOSE 3000

ENTRYPOINT ["json-server"]
CMD ["--help"]
