## Introdução ao Git

### Entendendo o que é Git e sua importância

1. Controle de Versão
2. Armazenamento em nuvem
3. Trabalho em equipe
4. Melhorar seu código
5. Reconhecimento

## Navegação via command line interface e instalação

### Comandos básicos para um bom desempenho no terminal

#### O que vamos aprender?
- Mudas de pastas
- Listar as pastas
- Criar pastas/arquivos
- Deletar pastas/arquivos

## Entendendo como o Git funciona por baixo dos panos

### Tópicos fundamentais para entender o funcionamento do Git

#### SHA1

A sigla SHA significa **Secure Hash Algorithm** (Algoritmo de Hash Seguro). É um conjunto de funções hash criptográficas projetadas pela NSA (Agência se Segurança Nacional dos EUA).

A encriptação gera um conjunto de caracteres indentificador de 40 dígitos que é único.

É uma forma curta de representar um arquivo.

![[Pasted image 20230326174925.png]]

### Objetos internos do Git

#### Blobs

![[Pasted image 20230326175611.png]]

Existe uma diferença entre usar a própria função do git para gerar o hash a patir da string "conteudo" e usar o sha1 do openssl, como podemos ver acima.

Isso acontece porque o git manipula os arquivo dentro objetos do tipo Blob, que guarda os metadados do arquivo. Eele guarda as informações como na imagem abaixo:

![[Pasted image 20230327081551.png]]

Nota-se que ele tem algumas informações a mais além da string conteudo, que  na imagem está representada pela string "Ola Mundo". Se passarmos para o sha1 do openssl a mesma string com os metadados, veremos que o hash gerado é igual ao do git:

![[Pasted image 20230327081740.png]]

#### Tree

As trees armazenam blobs, ou seja, é uma crescente. As blobs sendo o bloco basico de composição, a tree armazenando e apontando para tipos de blobs diferentes. Uma tree contém também metadados. Diferente da blob, as trees guardam o nome dos arquivos blobs. Elas também podem referenciar outras trees, assim como um diretório pode conter outros diretórios dentro.

![[Pasted image 20230327083023.png]]

Como a Tree também possui um SHA1 próprio, sempre um arquivo é alterado, isso faz com que  a blob tenha seu sha1 alterado, refletindo também no sha1 da Tree, que também será alterado.

![[Pasted image 20230327083303.png]]

#### Commit

Por fim, temos o objeto mais importante de todos. O commit é o obejto que vai juntar todos os outros objetos, ele quem vai dar sentido para alateração que estamos fazendo em todos os objetos.

Ele aponta para uma Tree, aponta para o ultimo commit feito antes dele, aponta para um autor e aponta para uma mensagem que descreve o que ele é.

![[Pasted image 20230327083620.png]]

Os commits também possuem um SHA1, guardando todos os metadados.


## Introdução ao Git

### Entendendo o que é Git e sua importância

1. Controle de Versão
2. Armazenamento em nuvem
3. Trabalho em equipe
4. Melhorar seu código
5. Reconhecimento

## Navegação via command line interface e instalação

### Comandos básicos para um bom desempenho no terminal

#### O que vamos aprender?
- Mudas de pastas
- Listar as pastas
- Criar pastas/arquivos
- Deletar pastas/arquivos

## Entendendo como o Git funciona por baixo dos panos

### Tópicos fundamentais para entender o funcionamento do Git

#### SHA1

A sigla SHA significa **Secure Hash Algorithm** (Algoritmo de Hash Seguro). É um conjunto de funções hash criptográficas projetadas pela NSA (Agência se Segurança Nacional dos EUA).

A encriptação gera um conjunto de caracteres indentificador de 40 dígitos que é único.

É uma forma curta de representar um arquivo.

![[Pasted image 20230326174925.png]]

### Objetos internos do Git

#### Blobs

![[Pasted image 20230326175611.png]]

Existe uma diferença entre usar a própria função do git para gerar o hash a patir da string "conteudo" e usar o sha1 do openssl, como podemos ver acima.

Isso acontece porque o git manipula os arquivo dentro objetos do tipo Blob, que guarda os metadados do arquivo. Eele guarda as informações como na imagem abaixo:

![[Pasted image 20230327081551.png]]

Nota-se que ele tem algumas informações a mais além da string conteudo, que  na imagem está representada pela string "Ola Mundo". Se passarmos para o sha1 do openssl a mesma string com os metadados, veremos que o hash gerado é igual ao do git:

![[Pasted image 20230327081740.png]]

#### Tree

As trees armazenam blobs, ou seja, é uma crescente. As blobs sendo o bloco basico de composição, a tree armazenando e apontando para tipos de blobs diferentes. Uma tree contém também metadados. Diferente da blob, as trees guardam o nome dos arquivos blobs. Elas também podem referenciar outras trees, assim como um diretório pode conter outros diretórios dentro.

![[Pasted image 20230327083023.png]]

Como a Tree também possui um SHA1 próprio, sempre um arquivo é alterado, isso faz com que  a blob tenha seu sha1 alterado, refletindo também no sha1 da Tree, que também será alterado.

![[Pasted image 20230327083303.png]]

#### Commit

Por fim, temos o objeto mais importante de todos. O commit é o obejto que vai juntar todos os outros objetos, ele quem vai dar sentido para alateração que estamos fazendo em todos os objetos.

Ele aponta para uma Tree, aponta para o ultimo commit feito antes dele, aponta para um autor e aponta para uma mensagem que descreve o que ele é.

![[Pasted image 20230327083620.png]]

Os commits também possuem um SHA1, guardando todos os metadados.


### Chaves SSH e Token

#### Chave SSH

Para gerar as chaves pública e privada, seguiremos os seguintes passos:

``` bash
ssh-keygen -t ed25519 -C email_usado_github
```

Onde o ed25519 é o tipo de chave e o e-mail deve ser o e-mail cadastrado no github.

