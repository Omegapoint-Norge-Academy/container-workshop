# Oppgave 6
Verifiser at monterte volumer ikke forsvinner når docker-containeren stoppes

<details>
  <summary>Hint</summary>

  `docker run --volume`
</details>

<details>
  <summary>Løsning</summary>

  ```
  ❯ mkdir persistent
  ❯ docker run -it -v ./persistent:/workfolder busybox
  / # echo "hello" > workfolder/test.txt

  ❯ cat persistent/test.txt
  hello
  ```
</details>
