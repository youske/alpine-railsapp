# Alpine Linux ruby on rails
FROM youske/alpine-stdmachine:base
MAINTAINER youske miyakoshi <youske@gmail.com>

LABEL com.stdmachine.description="alpine ruby image" \
      com.stdmachine.role="ruby image"

RUN PACKAGE='nginx ruby ruby-bundler ruby-irb libstdc++'  \
    BUILDPACKAGE='alpine-sdk build-base musl-dev ruby-dev make gcc g++ gfortran libffi-dev make cmake linux-headers' && \
    apk add --update --no-cache ${PACKAGE} && apk add --no-cache -t buildtool ${BUILDPACKAGE} && \
    echo 'gem: --no-document' >> /etc/gemrc && \
    echo "gem: --user-install --no-document" >> ~/.gemrc && \
    gem install unicorn --no-rdoc --no-ri && \
    apk del buildtool --no-cache && rm -rf /tmp/* /var/cache/apk/* /root/.wget-hsts
