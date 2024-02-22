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

  - Nome: Defini um nome significativo para a instância para facilitar sua identificação. (imagem 1)
  - AMI: Escolhi a Amazon Linux AMI porque ela possui uma otimização para desempenho em instâncias EC2 e vem com diversas ferramentas e utilitários AWS pré-instalados. Isso faz com que o tempo de configuração seja reduzido e a sobrecarga de manutenção também, além de oferecer melhor compatibilidade e performance com os serviços da AWS. (imagem 2)
  - Tipo de Instância: Escolhi o tipo de instância `t3.micro` por causa do seu equilíbrio entre custo e eficiência para casos de uso que não exigem recursos computacionais intensivos, que é o caso desta atividade. Os tipos `t2` foram projetados para forenecer uma quantidade moderada de capacidade de CPU base, permitindo aumentar o desempenho, utilizando créditos de CPU acumulados durante períodos de baixa utilização. (imagem 3)
  - Configuração de Rede: Optei por deixar as configurações padrçoes de VPC e sub-red, haja vista que o cenário atual da atividade não possui requisitos específicos de rede, de modo a simplificar o processo de implantação da instância de EC2. Porém, vale ressaltar que adicionei regras de segurança de modo a permitir tráfego HTTP e HTTPS, haja vista que é essencial para que tal instância seja acessada de forma segura pela internet. (imagem 4)
  - Par de Chaves: Criei um novo par de chaves do tipo `.ppk` para realizar a autenticação na instância EC2 via SSH. Isso faz com que a instância seja acessada somente se tiver a chave privada correspondente a ela, de modo a garantir uma segurança maior da instância, previnindo de acessos não autorizados. (imagem 5)
  - Armazenamento: Optei por deixar as configurações padrões de armazenamento de 8 GiB com um volume raiz gp3, pois no cenário atual da atividade não possui requisitos específicos de armazenamento. Ademais, tais configurações permitem um equilíbrio entre curso e desempenho, além de que os volumes gp3 são versáteis e oferecem um desempenho consistente para diferentes aplicações, caso esta instância fosse utilizada para algo específico.
- Após preencher tudo isso, é possível clicar em "Excutar instância"

<sub>Imagem 1 - Definição de nome EC2

![Espaço de definição de nome](/nome.png)

<sub>Imagem 2 - Seleçao da AMI </sub>

![Seleção da AMI](/ami.png)

<sub>Imagem 3 - Tipo de Instância</sub>

![Seleção do tipo de instância](/tipo.png)

<sub>Imagem 4 - Configurações de Rede</sub>

![Configurações de Rede](/rede.png)

<sub>Imagem 5 - Seleção do par de chaves</sub>

![Par de chaves](/chaves.png)

<sub>Imagem 6 - Tipo de Armazenamento</sub>

![Armazenaento](/armazenamento.png)

2. **Acesso à instância via SSH**:
Foi escolhido o software `Putty` para realizar o acesso via SSH à instância EC2 criada. Essa escolha se baseia no fato da simplicidade do software de realizar tal conexão, haja vista que é necessário somente o IP da máquina e a chave privada dela. Nesse sentido, o passo a passo listdo e ilustrado a seguir são referentes a esse software:
- Realizei a instalação do software Putty;
- Ao abrir o software, preenchi o campo `Host name (or IP address)` com o endereço IP público da instância criada (imagem 7)
- Depois, fui até `Auth`, dentro de `SSH`, e anexei o par de chaves criados anteriormente no formato `.ppk` (imagem 8)
- Logo após, cliquei em `Open`, resultado na abertura da conexão SSH

<sub>Imagem 7 - Preenchimento dos campos com o endereço IP Público da instância criada</sub>

![Dados da instância no Putty](/putty-ip.png)

<sub>Imagem 8 - Anexo do par de chaves no putty</sub>

![Par de chaves no putty](/putty-chave.png)

## Resultados

- **Criação da Instância EC2**
  ![Print da Instância Criada dentro do Painel da AWS](/dados-instancia.png)

- **Acesso via SSH com Putty realizado com sucesso**
  ![Print do Putty com o acesso à instância EC2 em conjunto com o IP público da instância](/putty.png)

- **IP privado da máquina EC2 criada**
  - IP Privado: 172.31.30.91

## Conclusão

A execução bem-sucedida deste projeto demonstrou a capacidade de criar e acessar uma instância EC2 na AWS usando SSH. Este processo reforça a importância de entender os serviços de computação em nuvem e as práticas de segurança necessárias para o gerenciamento eficaz de recursos na nuvem. A experiência adquirida aqui servirá como uma base sólida para futuros projetos envolvendo infraestrutura na AWS, inclusive para o projeto atual que está sendo desenvolvido para a Gerando Falcões.
