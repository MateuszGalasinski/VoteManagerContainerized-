FROM ethereum/client-go

RUN apk add --update git bash nodejs nodejs-npm perl

RUN cd /root &&\
    git clone https://github.com/cubedro/eth-net-intelligence-api &&\
    cd eth-net-intelligence-api &&\
    npm install &&\
    npm install -g pm2

RUN apk add git python make gcc g++ && \ 
    npm install -g truffle

WORKDIR /root
RUN git clone https://github.com/MateuszGalasinski/VoteManagerContract.git

# only for convenience when experimenting
RUN apk add nano 

WORKDIR /root
ADD start.sh /root/start.sh
ADD app.json /root/eth-net-intelligence-api/app.json
RUN chmod +x /root/start.sh

ENTRYPOINT /root/start.sh
