# Cluster Swarm com Vagrant

Este repositório contém a configuração para um Cluster Swarm local utilizando Vagrant e VirtualBox. O projeto envolve a criação de quatro máquinas virtuais: uma configurada como nó manager (master) e três como nós workers (node01, node02 e node03). 

## Objetivo

O objetivo deste projeto é proporcionar um ambiente eficiente para desenvolvimento e teste de aplicações Docker em um cluster, eliminando a necessidade de configurações manuais e melhorando a produtividade dos desenvolvedores.

## Estrutura do Projeto

- **Master**: Nó manager do cluster.
- **Node01, Node02, Node03**: Nós workers que se juntam ao cluster.

## Requisitos

- [Vagrant](https://www.vagrantup.com/downloads) instalado.
- [VirtualBox](https://www.virtualbox.org/) instalado.

## Instalação

1. Clone este repositório para o seu ambiente local:
   git clone <https://github.com/brusiqueiraagrocp/docker-swarm-cluster>
   cd <docker-swarm-cluster>

Execute o comando abaixo para iniciar as máquinas virtuais:
vagrant up

Configuração
O Vagrantfile contém as definições das máquinas virtuais. Cada máquina é configurada com um IP fixo e Docker pré-instalado. O nó master inicializa o cluster Docker Swarm, enquanto os nós workers se juntam ao cluster.

Vagrantfile
Aqui estão algumas configurações importantes:
Master (nó manager):
IP: 192.168.56.10
Docker inicializado com docker swarm init.

Workers:

IPs: 192.168.56.11, 192.168.56.12, 192.168.56.13
Se juntam ao cluster com o comando docker swarm join --token <TOKEN> 192.168.56.10:2377.
Uso
Após a configuração, você pode acessar as máquinas virtuais utilizando:

vagrant ssh master
ou
vagrant ssh node01
Substitua node01 pelo nome do nó desejado.

Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir um pull request ou relatar problemas.

Licença
Este projeto é licenciado sob a MIT License.

Contato
Se você tiver alguma dúvida ou sugestão, sinta-se à vontade para entrar em contato:

Nome: Bruno Gabriel Siqueira
Email: contato@brunosiqueira.tec.br
