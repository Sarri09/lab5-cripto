FROM ubuntu:14.10

RUN apt-get update && \
    apt-get install -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

EXPOSE 8080

CMD ["/bin/bash"]

