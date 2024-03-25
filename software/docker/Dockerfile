FROM lscr.io/linuxserver/code-server:latest
LABEL version="1.4.551"

# installing quarto
RUN curl -LO https://github.com/quarto-dev/quarto-cli/releases/download/v1.4.551/quarto-1.4.551-linux-amd64.deb \
    && apt install ./quarto-1.4.551-linux-amd64.deb -y \
    && rm quarto-1.4.551-linux-amd64.deb

# installing tinytex and chromiun

RUN quarto install tinytex && \
    quarto install chromium

# installing python and packages

RUN apt update && apt install python3 python3-pip -y
COPY ./requirements.txt ./requirements.txt
RUN pip3 install -r requirements.txt


# checking quarto for dependencies
# RUN quarto check
