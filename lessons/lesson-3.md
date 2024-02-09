# Aula 3 (add, diff, commit, push)

Nessa aula iremos aprender os comandos básicos de escrita do git, são eles: `add`, `commit` e `push`.

**No fim desse arquivo teremos um exercício prático antes de seguir para a próxima aula.**

## Add

Quando queremos adicionar um arquivo novo ou modificado ao repositório local precisamos usar o comando `add`, esse comando adiciona o arquivo ao que chamamos de `staging area` que é uma área de preparação para o commit.
Para adicionar o commit basta executar `git add <nome do arquivo>`.
Existem diversas formas de trabalhar com o add e podemos consultar todas elas usando o help `git add --help`.

Por exemplo:
  - `git add .`
  - `git add -A`
  - `git add --edit <arquivo>`


## Diff

Esse comando é usado para visualizar as diferenças entre o `working directory` e o `staging area`, para isso basta executar `git diff`.

De forma geral, usamos muito esse comando pra comparar o estado anterior vs  o que estamos modificando. Para instruções avançadas de como usar o diff, podemos consultar a documentação oficial do git [aqui](https://git-scm.com/book/pt-br/v2/Git-Essencial-Visualizando-Mudan%C3%A7as-no-Repository).

## Commit 

Após usar o comando `add` para adicionar os arquivos que queremos ao `staging area`, precisamos usar o comando `commit` para criar um commit com essas alterações. Conseguimos utilizar o comando `git status`, aprendido na aula anterior, para inclusive conferir quais arquivos estaremos adicionando no commit em questão.
Um commit é uma forma de agrupar alterações em um ponto específico do tempo, ele é composto por um hash, autor, data, mensagem e um ponteiro para o commit anterior. 

Pra mais informações sobre commits, podemos consultar a documentação oficial o git [aqui](https://git-scm.com/book/pt-br/v2/Git-Essencial-Gravando-Altera%C3%A7%C3%B5es-no-Reposit%C3%B3rio).

A forma mais simples de criar um commit, é utilizando o comando `git commit`. Porém, isso irá abrir um editor de texto integrado no terminal e isso pode num primeiro momento, ser um pouco confuso. para evitar que isso aconteça, podemos usar o comando `git commit -m "mensagem do commit"`, dessa forma o commit será criado com a mensagem que passamos como parâmetro, sem a necessidade de usar o editor integrado.

Assim como os demais comandos, o `git commit` também possui algumas opções que podemos consultar usando o help `git commit --help`.

## Push

O comando `push` é utilizado para enviar os commits criados para o repositório remoto. Para isso, basta executar `git push <remote> <branch>`, por exemplo: `git push origin main`.

Obs: por padrão, quando clonamos um repositório, o nome do remote é `origin`. Podemos consultar isso com o comando `git remote -v`.

# Prática 3

Se abrirmos o arquivo `README.md`, podemos perceber que ele está com um erro de digitação na linha da aula 3.
```markdown
3. [Pula 3 - comandos básicos de escrita (add, diff, commit, push)](lessons/lesson-3.md)
```

Vamos corrigir esse problema!
1. Com seu editor de preferencia, abra o arquivo `README.md` e corrija o erro de digitação.
2. Pra visualizar o status em funcionamento digite `git status`
3. Veja o diff das alterações usando `git diff` e confira se está alterando o que planeja.
4. Adicione o arquivo ao `staging area` usando o comando `git add README.md`.
5. Execute o `git diff` e `git status` novamente pra validar que não há mais diferenças entre o `working directory` e o `staging area`.
6. Crie um commit com a mensagem `feat: fix readme typo` usando o comando `git commit -m "feat: fix readme typo"`. Mas para isso, se lembre de adicionar a alteração realizada, com o comando `git add`.
7. Podemos visualizar o histórico de commits usando o comando `git log` ou `git log --oneline` (eu sempr prefiro o --one-line).
8. Com as mudanças realizadas localmente, precisamos enviar elas para o repositório remoto. Para isso, basta executar `git push origin lesson-3`.

--- 

Podemos seguir para a próxima aula na branch `lesson-4`.