[![Maven](https://img.shields.io/maven-metadata/v/http/central.maven.org/maven2/org/jooby/jooby-elasticsearch/maven-metadata.xml.svg)](http://mvnrepository.com/artifact/org.jooby/jooby-elasticsearch/1.6.3)
[![javadoc](https://javadoc.io/badge/org.jooby/jooby-elasticsearch.svg)](https://javadoc.io/doc/org.jooby/jooby-elasticsearch/1.6.3)
[![jooby-elasticsearch website](https://img.shields.io/badge/jooby-elasticsearch-brightgreen.svg)](http://jooby.org/doc/elasticsearch)
# elasticsearch

Open Source, Distributed, RESTful Search Engine via [Elastic Search](https://github.com/elastic/elasticsearch).

## exports

* ```RestClient```

## dependency

```xml
<dependency>
  <groupId>org.jooby</groupId>
  <artifactId>jooby-elasticsearch</artifactId>
  <version>1.6.3</version>
</dependency>
```

## usage

```java
{
  use(new Elasticsearch("localhost:9200"));
}
```

The constructor field is an array, so you can specify several hosts for round robin of requests.

## client API

The module exports a ```RestClient``` instance.

```java

put("/:id", req -> {
  // index a document
  RestClient client = require(RestClient.class);
  StringEntity data = new StringEntity("{\"foo\":\"bar\"}");
  return client.performRequest("PUT", "/twitter/tweet/" + req.param("id").value(), Collections.emptyMap(), data)
    .getEntity().getContent();
});
```
