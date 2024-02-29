# Oppgave 2

1. Lag en Dockerfile som bruker `alpine:latest` som base image.
1. Installer `curl` (`apk add curl`)
1. Sett entrypoint til å kjøre `curl`
1. Bygg Docker imaget
1. Bruk containeren til å kjøre curl

<details>
<summary>Hint 1</summary>

```
❯ docker build -t curler .
```
</details>

<details>
<summary>Hint 2</summary>

```
❯ docker run curler <url>
```
</details>

<details>
<summary>Løsning</summary>

```
FROM alpine:latest
RUN apk add curl
ENTRYPOINT ["curl"]
```
</details>