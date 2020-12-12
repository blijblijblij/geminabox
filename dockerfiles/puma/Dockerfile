FROM ruby:2.7.2

RUN gem install geminabox -v 1.2.0
RUN mkdir -p /webapps/geminabox/config && \
	mkdir -p /webapps/geminabox/data

RUN mkdir -p /tmp
RUN chmod o+t /tmp

RUN gem install puma

WORKDIR /webapps/geminabox/config
COPY assets/conf/config.ru /webapps/geminabox/config/config.ru

# default server config
COPY assets/server_config/config.ru /webapps/server/config/config.ru

COPY assets/entrypoint.sh /webapps/server

ENTRYPOINT ["/webapps/server/entrypoint.sh"]
