# Oppgave 4

Start en container med nettverksmodus "None" og verifiser at kun loopback-grensesnittet er tilgjengelig


<details>
  <summary>Hint 1</summary>

  ```
  --network=none
  ```
</details>

<details>
  <summary>Hint 2</summary>

  ```
  ifconfig
  ```
</details>

<details>
  <summary>Løsing</summary>
  
  ```
  docker run --name nonetwork  --network=none -d praqma/network-multitool
  
  docker exec -it nonetwork /bin/sh

  ifconfig
  ```
</details>

