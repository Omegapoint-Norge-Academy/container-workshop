# Oppgave 3
Bygg en dockerfile som kjører applikasjonen "hello-world"

1. Bruk `scratch` som base-image
1. Kopier inn applikasjonen
1. Bruk ENTRYPOINT for å kjøre applikasjonen



<details>
<summary>Løsning</summary>

```
FROM scratch
COPY hello-world /

ENTRYPOINT ["/hello-world"]
```
</details>


## Ekstraoppgave
Benytt flerstegs-bygg for å først kompilere `.go`-fila, før du kopierer denne til et image basert på `scratch`

<details>
<summary>Hint 1</summary>
Bruk `golang:1.18` som base image for byggsteget
</details>

<details>
<summary>Hint 2</summary>

```
FROM golang:1.18 AS builder

[...]
FROM runtime
COPY --from=builder /app/hello-world /
```
</details>

<details>
<summary>Løsning</summary>

```
# Build stage
FROM golang:1.18 AS builder
WORKDIR /app
COPY hello-world.go .
RUN go build -o hello-world hello-world.go

# Runtime stage
FROM scratch
COPY --from=builder /app/hello-world /
ENTRYPOINT ["/hello-world"]
```
</details>


[Neste oppgave](/oppgave-4/README.md)