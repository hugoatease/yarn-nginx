FROM node:6.7

RUN apt-get update -y && apt-get install -y nginx git
RUN curl -o- -L https://yarnpkg.com/install.sh | bash
ENV PATH "$PATH:/root/.yarn/bin"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY package.json yarn.lock /usr/src/app/
ONBUILD RUN yarn install
ONBUILD COPY . /usr/src/app

CMD ["yarn", "start"]
