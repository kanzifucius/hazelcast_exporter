# hazelcast_exporter

A [prometheus](https://prometheus.io) exporter for
[Hazelcast IMDG](https://hazelcast.org/).

## Usage

`hazelcast_exporter --listen :8080 --config hazelcast.yml`

Then, point your Prometheus server to `:8080/metrics`.

## Configuration

```
hazelcastUrl: 127.0.0.1:5780
hazelcastClusterName: group-1
hazelcastClusterPassword: password-1
hazelcastMaps:
- tokens
```

## Installation

```
go get -u github.com/golang/dep/cmd/dep
dep ensure
go get -u github.com/inuits/hazelcast_exporter
```

### Metrics

```
hazelcast_up
```
1 or 0 wether the connection to hazelcast is successful.

```
hazelcast_members
```
Number of members in the hazelcast cluster.


```
hazelcast_map_items
```
Number of items in a specific map.

### Known bugs

This program is crashing because of
[https://github.com/hazelcast/hazelcast-go-client/issues/242](https://github.com/hazelcast/hazelcast-go-client/issues/242).
