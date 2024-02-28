# Oppgave 6
Verifiser at monterte volumer ikke forsvinner når docker-containeren stoppes

<details>
  <summary>Hint</summary>

  `docker run --volume`
</details>

<details>
  <summary>Løsning</summary>

  `docker run -it -v ./persistent:/workfolder busybox`
</details>
