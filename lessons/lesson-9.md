# Aula 9 (submodule)

Eventualmente precisamos trabalhar com repositórios dentro de repositórios, por exemplo, quando temos um projeto que depende de outro projeto.
Gerenciar multiplos repositórios com dependencias localmente pode ser um pouco trabalhoso, mas o git nos ajuda com isso através do recurso de `submodules`.

**No fim desse arquivo teremos um exercício prático antes de seguir para a próxima aula.**

## Submodule

O comando `git submodule` nos permite adicionar repositórios como dependencias de outros repositórios.
Na prática isso significa que podemos adicionar a referencia de um repositório dentro de outro repositório e assim podemos trabalhar com os dois repositórios de forma independente porém localmente parecem ser um único repositório.

É importante ressaltar que o repositório adicionado é uma referencia com sua própria árvore de commits e branchs e para gerenciar o estado desse submódulo é necessário entrar no diretório do submódulo e executar os comandos git normalmente.

Na prática iremos explorar um pouco mais afundo o uso de submodules e como gerenciar o estado deles.

Como usar:
```bash
git submodule add <url-do-repositório> <caminho-para-o-submódulo>
```

Documentação mais avançada: https://git-scm.com/docs/git-submodule/pt_BR

# Prática 9

Nessa prática iremos criar um novo submodulo do repositório `lucianopf/git-workshop-conclusion` e manipular esse submodulo conforme nossas necessidades.

Para isso precisamos fazer o seguinte:
1. Vamos só dar uma conferidinha no outro repo no Github https://github.com/lucianopf/git-workshop-conclusion
2. Para criar o submódulo vamos executar o comando `git submodule add git@github.com:lucianopf/git-workshop-conclusion.git conclusion`.
3. Rode o comando `git status` na raiz do seu projeto e dentro do folder `conclusion` e repare a diferença das braches onde na raiz estamos na branch `lesson-9` e no folde conclusion estamos na `main`.
4. Para análise posterior vamos criar um commit com esse novo submódulo em nossa branch, pra isso basta retornar pra raiz do projeto e executar o comando `git add conclusion` e `git commit -m "feat: add conclusion submodule"`.
4. Nesse outro repositório temos a branch também chamada `lesson-9-conclusion` mas pra garantir que trouxemos tudo que precisa vamos para dentro da pasta conclusion e usaremos o `git fetch --all` e depois `git checkout lesson-9-conclusion` e podemos perceber que dentro da pasta conclusion agora temos um arquivo chamado `conclusion.md`
5. Rode o comando `git status` dentro da pasta `conclusion` e vai perceber que não há nada pra ser commitado entretanto volta na raiz e repita o processo e vai perceber que na raiz o resultado é que temos diferenças no folder `conclusion`.
6. Vamos adicionar essas mudanças e fazer um commit, pra isso basta executar o comando `git add conclusion` e `git commit -m "feat: update conclusion"`.
7. Vamos dar push na branch `lesson-9` e depois vamos no Github. 

Vamos seguir pra análise do que foi feito no Github e ter uma visão mais completa do processo.
Vamos para a branch `lesson-9` e vamos ver a ordem dos commits pra conseguir ver o estado do repositório a cada passo executado.

Olhando o repositório partindo do commit `feat: lesson-9` percebemos na estrutra de arquivos que não temos nenhuma referencia a pasta `conclusion` pois nesse momento ainda não adicionamos esse submódulo.

Olhando o repositório partindo do commit `feat: add conclusion submodule` podemos ver que agora temos uma pasta chamada `conclusion` que é um pouco diferente das demais e nela existe um shorthash que é a referencia do commit que está sendo referenciado no submodulo naquele momento. 
Em parelo vamos abrir o repositório https://github.com/lucianopf/git-workshop-conclusion e reparar no last commit da branch `main` que deve ser o mesmo shorthash que temos no nosso repositório.

Olhando o repositório partindo do commit `feat: update conclusion` percebemos que temos algo bem semelhante ao commit anterior só que agora a referencia de um shorhash diferente.
Vamos na outra aba onde temos aberto o `git-workshop-conclusion` e vamos ver o last commit da branch `lesson-9-conclusion` que deve ser o mesmo shorthash que temos no nosso repositório.
 
Com isso podemos concluir que o submódulo é uma referencia pra um commit de outro repositório e que podemos trabalhar com esses repositórios de forma independente.

--- 

**PARABÉNS PELO TRABALHO, CONCLUÍMOS AS AULAS OFICIAIS DO WORKSHOP!**

Temos uma aulinha extra um pouco mais dedicada a explorar a interface e processos do Github que está na branch `lesson-10`. 