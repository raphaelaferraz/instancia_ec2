# Relatório Técnico sobre Acesso SSH no EC2

## Introdução

Este relatório descreve o processo de criação de uma instância de máquina virtual EC2 (Elastic Compute Cloud) na Amazon Web Services (AWS) e o acesso a esta máquina utilizando o protocolo SSH (Secure Shell) através da ferramenta PUTTY. A motivação principal deste procedimento é demonstrar a capacidade de provisionar e gerenciar recursos de computação na nuvem de forma segura e eficiente.

## Objetivo

- Criar uma instância EC2 na AWS;
- Estabelecer uma conexão SSH segura com a instância;
- Documentar todo o processo, incluindo capturas de tela relevantes, para demonstrar competência no gerenciamento de criação de instâncias na AWS.

## Materiais

- **Amazon Web Services (AWS) Account**: Uma conta na AWS para criar e gerenciar recursos;
- **PUTTY**: Uma ferramenta gratuita de emulação de terminal e cliente SSH para Windows;
- **Computador com acesso à Internet**: Para acessar o console da AWS e a ferramenta PUTTY.

## Método

O passo a passo listado abaixo foi utilizado para obter os resultados que serão listados a seguir.

1. **Criação da Instância EC2**:

- Acessei a Página incial do Console da AWS;
- Procurei o serviço "EC2" e selecioná-lo;
- Selecionei "Executar Instância" para criar uma nova instância;
- Na página "Launch an instance" preenchi as seguintes informações:
  - Nome, que se refere ao nome da Instância
  - A imagem da máquina da amazon (Amazon Linux)
  - Criei um novo par de chaves para o login. Essa chave deve ser do tipo `.ppk`
  - Selecionei, em Configurações de Rede, a habilitação do tráfego HTTPS e HTTP para internet
- Após preencher tudo isso, é possível clicar em "Excutar instância"

2. **Acesso à instância via SSH**:

- Realizei a instalação do software Putty;
- Ao abrir o software, preenchi o campo `Host name (or IP address)` com o endereço IP público da instância criada
- Depois, fui até `Auth`, dentro de `SSH`, e anexei o par de chaves criados anteriormente no formato `.ppk`
- Logo após, cliquei em `Open`, resultado na abertura da conexão SSH

## Resultados

- **Criação da Instância EC2**
  ![Print da Instância Criada dentro do Painel da AWS](/dados-instancia.png)

- **Acesso via SSH com Putty realizado com sucesso**
![Print do Putty com o acesso à instância EC2 em conjunto com o IP público da instância](/print-putty.png)

## Conclusão

A execução bem-sucedida deste projeto demonstrou a capacidade de criar e acessar uma instância EC2 na AWS usando SSH. Este processo reforça a importância de entender os serviços de computação em nuvem e as práticas de segurança necessárias para o gerenciamento eficaz de recursos na nuvem. A experiência adquirida aqui servirá como uma base sólida para futuros projetos envolvendo infraestrutura na AWS, inclusive para o projeto atual que está sendo desenvolvido para a Gerando Falcões. 
