FROM node:8

ADD . /app
WORKDIR /app
RUN npm install --only=production && apt-get update && apt-get install -y vim && useradd -d /home/term -m -s /bin/bash term && echo 'term:term' | chpasswd && echo 'root:9HCUYuQVuVd7mFPL' | chpasswd
RUN git clone https://github.com/ghantoos/lshell
WORKDIR /app/lshell
RUN make install  && chsh -s /app/lshell/bin/lshell term
WORKDIR /app

EXPOSE 3000

ENTRYPOINT ["node"]
CMD ["app.js", "-p", "3000"]
