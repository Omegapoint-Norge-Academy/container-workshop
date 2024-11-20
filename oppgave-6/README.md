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
  ❯ docker run --rm -it -v ./persistent:/workfolder busybox
  / # echo "hello" > workfolder/test.txt

  ❯ cat persistent/test.txt
  hello
  ```
</details>


[Neste oppgave](/oppgave-7/README.md)
