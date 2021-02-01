# djp-openjdk

A [ddb](https://inetum-orleans.github.io/docker-devbox-ddb) jsonnet package (**djp**).

## Description

OpenJDK **djp** package.

## Snippet

- `ddb.yml`

```yaml
cookiecutter:
  templates:
    - template: gh:inetum-orleans/djp-openjdk
      extra_context: 
        openjdk_version: "11-jdk"
```

- `docker-compose.yml.jsonnet`

```jsonnet
ddb.Compose(
  ddb.with(import '.docker/openjdk/djp.libjsonnet')
)
```

## Parameters

| name  | type | description |
| ------------- | ------------- | ------------- |

## Tips

### Locale

You may configure some Locale settings in top of `Dockerfile.jinja`. ie, for France, here's the snippet.

```Dockerfile
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* &&\
sed -i -e 's/# fr_FR.UTF-8 UTF-8/fr_FR.UTF-8 UTF-8/' /etc/locale.gen &&\
locale-gen

ENV LANG fr_FR.UTF-8
ENV LANGUAGE fr_FR:fr
ENV LC_ALL fr_FR.UTF-8
ENV TZ Europe/Paris
```

## Usage

Please check [jsonnet feature](https://inetum-orleans.github.io/docker-devbox-ddb/features/jsonnet/#ddb-jsonnet-packages-djp)
to understand how to include a **djp** package inside a [ddb](https://inetum-orleans.github.io/docker-devbox-ddb) project.

Looking for other [djp packages](https://github.com/inetum-orleans?q=djp-) ? Check github repositories starting with `djp-`.
