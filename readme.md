# Compilador CMM

Um compilador simples para uma linguagem imperativa semelhante a C. O compilador gera código assembly de 32 bits para Linux.

## Autores

- Gabriel Zurawski
- Anderson Sprenger

## Requisitos

Para construir e executar o projeto, você precisará de um ambiente Linux (testado em Ubuntu) com as seguintes ferramentas instaladas:

- **JDK (Java Development Kit)** para compilar e executar o parser
- **build-essential** (ou pelo menos `make`, `as` e `ld`)
- O arquivo `JFlex.jar` deve estar no diretório raiz do projeto
- O binário `yacc.linux` deve estar no diretório raiz do projeto

## Como Executar

Siga os passos abaixo a partir de um terminal no diretório raiz do projeto.

### 1. Preparar os Arquivos

Primeiro, dê permissão de execução para o binário do Byacc/j e para o script de execução:

```bash
chmod +x yacc.linux
chmod +x run.x
```

### 2. Compilar o Compilador

Use o Makefile para gerar os analisadores léxico/sintático e compilar todas as classes Java do projeto:

```bash
make
```

### 3. Compilar um Programa .cmm

Use o script `run.x` para compilar um dos arquivos de teste (por exemplo, `testeBreakContinue.cmm`). Este script irá executar o compilador, gerando um arquivo de assembly (`.s`) e, em seguida, montando e ligando-o para criar um executável:

```bash
./run.x testeBreakContinue.cmm
```

### 4. Executar o Programa Gerado

Após a execução bem-sucedida do passo anterior, um novo arquivo executável terá sido criado no diretório (neste caso, `testeBreakContinue`). Para executá-lo:

```bash
./testeBreakContinue
```

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

- Arquivos de teste com extensão `.cmm`
- Scripts de compilação e execução
- Código fonte do compilador em Java
- Ferramentas auxiliares (JFlex, Byacc/j)

## Observações

- O compilador foi testado especificamente em ambiente Ubuntu Linux
- Certifique-se de que todas as dependências estão instaladas antes de executar
- Os arquivos executáveis gerados são específicos para arquitetura de 32 bits