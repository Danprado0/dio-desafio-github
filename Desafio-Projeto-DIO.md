

# Desafio de Projeto DIO

### Git e Github

##### 

#### Principais pontos Git

### 

##### Configuração inicial git

- **Teste as configurações**: git config --list

- A primeira coisa que você deve fazer ao instalar Git é configurar seu nome de usuário e endereço de e-mail. Isto é importante porque cada *commit* usa esta informação, e ela é carimbada de forma imutável nos *commits* que você começa a criar:

  - ```console
    $ git config --global user.name "Fulano de Tal"
    $ git config --global user.email fulanodetal@exemplo.br
    ```

- Como pedir ajuda: 
  - git help <verb> 
  - git <verb> --help

Como obter um repositório Git

Você pode obter um projeto Git utilizando duas formas principais. 1. Você pode pegar um diretório local que atualmente não está sob controle de versão e transformá-lo em um repositório Git, ou 2. Você pode fazer um *clone* de um repositório Git existente em outro lugar.

###### Repositório de um diretório existente

```console
$ cd /c/user/your_repository
```

Isso cria um novo subdiretório chamado `.git` que contém todos os arquivos necessários de seu repositório – um esqueleto de repositório Git. Neste ponto, nada em seu projeto é monitorado ainda.

Se você quer começar a controlar o versionamento dos arquivos existentes (ao contrário de um diretório vazio), você provavelmente deve começar a monitorar esses arquivos e fazer um *commit* inicial. Você pode fazer isso com alguns comandos `git add` que especificam os arquivos que você quer monitorar, seguido de um `git commit`:

```console
$ git add *.c
$ git add LICENSE
$ git commit -m 'initial project version'
```

###### Clonando um repositório existente

Caso você queira obter a cópia de um repositório Git existente – por exemplo, um projeto que você queira contribuir – o comando para isso é `git clone`.

Você clona um repositório com `git clone [url]`. Por exemplo, caso você queria clonar a biblioteca Git Linkable chamada libgit2, você pode fazer da seguinte forma:

```console
$ git clone https://github.com/libgit2/libgit2
```



###### Verificando o status de seus arquivos

A principal ferramenta que você vai usar para determinar quais arquivos estão em qual estado é o comando `git status`

Para começar a rastrear um novo arquivo, você deve usar o comando `git add`. Para começar a rastrear o arquivo README, você deve executar o seguinte:

```console
$ git add README
```

Executando o comando *status* novamente, você pode ver que seu README agora está sendo rastreado e preparado (*staged*) para o *commit*:

```console
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   README
```

Se você fizer um *commit* neste momento, a versão do arquivo que existia no instante em que você executou `git add`, é a que será armazenada no histórico de *snapshots*. Você deve se lembrar que, quando executou `git init` anteriormente, em seguida, você também executou `git add (arquivos)` - isso foi para começar a rastrear os arquivos em seu diretório. O comando `git add` recebe o caminho de um arquivo ou de um diretório. Se for um diretório, o comando adiciona todos os arquivos contidos nesse diretório recursivamente.



###### Fazendo  *commit* de suas alterações

Agora que sua área de *stage* está preparada do jeito que você quer, você pode fazer *commit* das suas alterações. Lembre-se que qualquer coisa que ainda não foi enviada para o *stage* — qualquer arquivo que você tenha criado ou alterado e que ainda não tenha sido adicionado com `git add` — não entrará nesse *commit*. Esses arquivos permanecerão no seu disco como arquivos alterados. Nesse caso, digamos que, da última vez que você executou `git status`, você viu que tudo estava no *stage*, então você está pronto para fazer *commit* de suas alterações. O jeito mais simples de fazer *commit* é digitar `git commit`:

```console
$ git commit
```



Alternativamente, você pode digitar sua mensagem de *commit* diretamente na linha de comando, depois da opção `-m` do comando `commit`, assim:

```console
$ git commit -m "Story 182: Fix benchmarks for speed"
[master 463dc4f] Story 182: Fix benchmarks for speed
 2 files changed, 2 insertions(+)
 create mode 100644 README
```

Você acaba de criar seu primeiro *commit*! Veja que a saída do comando fornece algumas informações: em qual *branch* foi feito o *commit* (`master`), seu *checksum* SHA-1 (`463dc4f`), quantos arquivos foram alterados e estatísticas sobre o número de linhas adicionadas e removidas.

Lembre-se de que o *commit* grava o *snapshot* que você deixou na área de *stage*. Qualquer alteração que você não tiver mandado para o *stage* permanecerá como estava, em seu lugar; você pode executar outro *commit* para adicioná-la ao seu histórico. Toda vez que você executa um *commit*, você está gravando um *snapshot* do seu projeto que você pode usar posteriormente para fazer comparações, ou mesmo restaurá-lo.





##### Principais atalhos

- git config --global user.name "Fulano de Tal" - (Altera nome do username)
- git config --global user.email fulanodetal@exemplo.br - (Altera e-mail do usuário)
- git help <verb> - (Solicitar ajuda de algum comando) 
- git init  - (Cria um novo repositório)
- git add <file-name> - (começar a monitorar esses arquivos e fazer um *commit* inicial.)
- git clone -  (Faz um clone de um repositório através de uma url, por exemplo)
- git status - (Verifica o status dos arquivos)
- git commit - (grava um *snapshot* do seu projeto)







Trechos extraídos da [documentação git](https://git-scm.com/doc)  