FROM opensearchproject/opensearch:1.2.4

RUN bin/opensearch-plugin install -b analysis-icu && \
    bin/opensearch-plugin install -b analysis-phonetic

RUN rm -rf /usr/share/opensearch/plugins/opensearch-security

EXPOSE 9200