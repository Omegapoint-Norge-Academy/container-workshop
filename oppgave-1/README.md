# Oppgave 1

Kjør `nginx` i en Docker-container, eksponer port 80 og last eksempelsiden i nettleseren din

<details>
<summary>Løsning</summary>

```
❯ docker run -p 80:80 nginx
❯ curl localhost
```
</details>


[Neste oppgave](/oppgave-2/README.md)