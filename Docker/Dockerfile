FROM ubuntu:24.04
ARG DEBIAN_FRONTEND noninteractive

RUN echo ttf-mscorefonts-installer msttcorefonts/accepted-mscorefonts-eula select true | debconf-set-selections

RUN apt-get update && apt-get install --no-install-recommends -y \
  make \
  texlive-xetex \
  texlive-science \
  texlive-font-utils \
  ghostscript \
  texlive-lang-european \
  texlive-latex-recommended \
  texlive-latex-extra \
  #texlive-fonts-extra \
  texlive-bibtex-extra \
  biber \
  imagemagick \
  pdftk \
  ttf-mscorefonts-installer \
  fontconfig \
&& apt-get clean && rm -rf /var/lib/apt/lists/* \
&& sed -i '/^<\/policymap>/i   <policy domain="coder" rights="read | write" pattern="PDF" \/>' /etc/ImageMagick-6/policy.xml
