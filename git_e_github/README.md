# GIT


## Conceitos principais
- SHA1: Secure Hash Algorithm
- Blobs
- Trees
- Commits

### Blobs

SHA1 de um conteúdo mais "blob \0[conteudo]". Exemplo:

    echo conteudo | git hash-object --stdin

equivale a

    echo -e 'blob 9\0conteudo | openssl sha1

### Trees
Guardam os metadados do arquivo do nome etc.

### Commits
Apontam para:
- Trees
- Autor
- Parent (commit anterior)
- Mensagem
- Timestamp
- etc

## Ciclo de vida no GIT

### Untracked
Arquivos não rastrados

### Tracked
Dividem-se em:
- Unmodified
- Modified
- Staged

O comando *git add* adiciona os arquivos untracked e modified para stage.
Arquivos staged estão esperando por um commit (*git commit*), que depois os retorna para unmodified. Além disso, o commit move os arquivos da staging area e os coloca no repo local.

## Conflito de Merge
Quando duas ou mais pessoas estão trabalhando em um projeto, pode ocorrer o que se chama de "conflito de merge", que consiste em uma tentativa de push no remote repo que não é finalizada devido a um commit anterior que altera um arquivo na mesma linha, ou seja, o arquivo está desatualizado.
A solução é usar o comando git pull para atualizar e sincronizar a versão do repositório local com o remoto, fazer as devidas alterações então realizar o push.