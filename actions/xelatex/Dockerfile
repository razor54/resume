FROM debian:bullseye

LABEL "maintainer"="Rahul Rai <rahulrai@live.com>"
LABEL "repository"="https://github.com/rahulrai-in/csf-resume-ops"
LABEL "homepage"="https://github.com/rahulrai-in/csf-resume-ops"

LABEL "com.github.actions.name"="Convert to PDF"
LABEL "com.github.actions.description"="Convert documents to PDF using xelatex."
LABEL "com.github.actions.icon"="code"
LABEL "com.github.actions.color"="blue"

# Install all xelatex and LaTeX dependencies
RUN apt-get update && \
    apt-get install --yes --no-install-recommends \
    fonts-ebgaramond-extra \
    texlive-fonts-extra \
    texlive-latex-extra \
    texlive-latex-recommended \
    texlive-fonts-recommended \
    texlive-plain-generic \
    texlive-lang-english \
    texlive-full \
    xzdec \
    texlive-xetex \
    && update-texmf \
    && texhash \
    && apt-get clean \
    #&& rm -rf /var/lib/apt/lists/*
    && apt-get autoclean && apt-get --purge --yes autoremove && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]