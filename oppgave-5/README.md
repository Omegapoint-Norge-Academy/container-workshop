# Oppgave 5
Start to containere i samme nettverk og verifiser at service discovery fungerer (container-navn kan brukes for DNS-oppslag)


<details>
  <summary>Hint</summary>
  Let i presentasjonen
</details>

<details>
  <summary>Løsing</summary>
  
  ```
  ❯ docker run --name web1  --network=mynet -d praqma/network-multitool 
  ❯ docker run --name web2  --network=mynet -d praqma/network-multitool 
  ❯ docker exec -it web1 /bin/sh
  / # ping web2
  ```
</details>

[Neste oppgave](/oppgave-6/README.md)