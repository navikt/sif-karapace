# sif-karapace

This project is based on the work of https://github.com/nais/karapace to provide an easy access to the aiven kafka rest api.

## Karapace

This is a packaging of [Aiven Karapace](https://github.com/aiven/karapace) for use as a REST API for Kafka in the NAIS platform together with [Kafkarator](https://github.com/nais/kafkarator).

Aiven uses Karapace to provide a REST API and Schema Registry for their managed Kafka offering.

## Access control

In order to be able to call sif-karapace, make sure to add your k8s service in the inbound rules located [here](https://github.com/navikt/sif-karapace/blob/main/nais/naiserator.yaml#L30).

## Usage

Karapace provides the same API as the Confluent Kafka REST proxy (v1). The [Confluent REST Proxy API Reference](https://docs.confluent.io/platform/current/kafka-rest/api.html) should be fairly accurate, but differences may be documented in the [Aiven Karapace project](https://github.com/aiven/karapace). See also this [issue](https://github.com/aiven/karapace/issues/181#issuecomment-828210804).

Karapace will be available using a service address in the cluster (http://application-name.namespace/), assuming you have set proper access policies.

### Examples
To be able to use this service, exec into the k8s pod (which you have granted access to).

#### List topics:

```shell
curl "http://sif-karapace/topics"
```

#### Get info for one particular topic:

```shell
curl "hhttp://sif-karapace/topics/my_topic"
```

For more info check out [Confluent REST Proxy API Reference](https://docs.confluent.io/platform/current/kafka-rest/api.html).
