# Container Images and Compose File for SolrWayback

SolrWayback: https://github.com/netarchivesuite/solrwayback
Sorl: https://solr.apache.org/
WARC Indexer: https://github.com/ukwa/webarchive-discovery/tree/master/warc-indexer

This repository contains the files to build the container images ([`Containerfile`](https://github.com/containers/common/blob/main/docs/Containerfile.5.md) also known as [Dockerfile](https://docs.docker.com/reference/dockerfile/)) for solrwayback, solr, and the warc-indexer to run them in a container engine (e.g. [podman](https://podman.io/), [docker](https://www.docker.com/), [buildah](https://buildah.io/), …) also a [compose file](https://compose-spec.io/) (`compose.yaml`) is provided to demonstrate the interplay of the containers.

## WARC Indexer

`SOLR_URL`: The URL under which the warc indexer can reach solr.
`STATUS_ROOT`: The path under which the warc indexer should store the satus information.

## Solr

`SOLR_HEAP=1G`: Increase the memory allocated by solr (solr default is 512m, for tests I set it to 1G, solrwayback recommends 4G)

## SolrWayback

The configuration of solrwayback happens in the properties files which are located in `solrwayback/properties/`.
The option `solr.server=http://solr:8983/solr/netarchivebuilder/` tells SolrWayback how to reach solr from within the container.
