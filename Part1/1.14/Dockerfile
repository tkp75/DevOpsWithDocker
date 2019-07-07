FROM noonat/rbenv-nodenv
EXPOSE 3000
ENV RBENV_VERSION 2.6.0-preview2
ENV NODENV_VERSION  10.4.0
ENV BUNDLER_VERSION 1.17.2
ENV RAILS_LOG_TO_STDOUT=true
RUN rbenv install ${RBENV_VERSION} && \
    CONFIGURE_OPTS="--disable-install-doc" rbenv global ${RBENV_VERSION} && \
    gem install bundler -v ${BUNDLER_VERSION} && \
    nodenv install ${NODENV_VERSION} && \
    nodenv global ${NODENV_VERSION}
COPY . .
RUN bundle install
RUN rails db:migrate
CMD rails s
