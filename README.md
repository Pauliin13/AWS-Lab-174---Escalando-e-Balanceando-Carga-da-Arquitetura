# ---Escalando-e-Balanceando-Carga-da-Arquitetura


## Visão Geral

Este projeto demonstra a implementação de uma arquitetura escalável e altamente disponível utilizando serviços da Amazon Web Services (AWS).

O laboratório teve como foco principal a utilização de:

* Amazon EC2
* Amazon Machine Image (AMI)
* Elastic Load Balancer (ELB)
* Auto Scaling Groups
* Launch Templates
* Amazon CloudWatch
* Arquitetura de Alta Disponibilidade

O ambiente foi configurado para distribuir automaticamente o tráfego entre múltiplas instâncias EC2 e escalar a infraestrutura dinamicamente com base na utilização de CPU.

---

# Arquitetura

## Arquitetura Inicial

* 1 instância EC2
* Subnet pública
* Escalabilidade manual
* Ponto único de falha

## Arquitetura Final

* Application Load Balancer (ALB)
* Múltiplas instâncias EC2
* Auto Scaling Group
* Instâncias distribuídas em subnets privadas
* Múltiplas Availability Zones
* Monitoramento com CloudWatch
* Escalabilidade automática

---

# Serviços AWS Utilizados

| Serviço               | Finalidade                                                |
| --------------------- | --------------------------------------------------------- |
| Amazon EC2            | Hospedagem das instâncias da aplicação                    |
| Amazon AMI            | Template utilizado para criação automática das instâncias |
| Elastic Load Balancer | Distribuição de tráfego entre servidores                  |
| Auto Scaling Group    | Escalabilidade automática e recuperação de falhas         |
| Launch Template       | Padronização das configurações das instâncias             |
| Amazon CloudWatch     | Monitoramento e criação de alarmes                        |
| Amazon VPC            | Isolamento e segmentação da rede                          |

---

# Objetivos do Laboratório

* Criar uma AMI a partir de uma instância EC2
* Configurar um Application Load Balancer
* Criar um Launch Template
* Configurar um Auto Scaling Group
* Implantar instâncias em subnets privadas
* Configurar monitoramento com CloudWatch
* Testar o escalonamento automático da infraestrutura

---

# Etapas Realizadas

## 1. Criação da AMI

Foi criada uma Amazon Machine Image (AMI) da instância Web Server existente, permitindo replicar automaticamente servidores idênticos durante o processo de Auto Scaling.

## 2. Configuração do Load Balancer

Foi configurado um Application Load Balancer (ALB) distribuído entre duas subnets públicas para balancear o tráfego HTTP entre múltiplas instâncias EC2.

## 3. Criação do Launch Template

O Launch Template foi criado contendo:

* AMI personalizada
* Tipo da instância
* Security Group
* Configurações padrão de implantação

## 4. Configuração do Auto Scaling Group

O Auto Scaling Group foi configurado com:

* Mínimo de instâncias: 2
* Quantidade desejada: 2
* Máximo de instâncias: 4

O grupo realiza o aumento ou redução automática da infraestrutura conforme a demanda da aplicação.

## 5. Monitoramento com CloudWatch

Foram utilizados alarmes do CloudWatch para monitorar a utilização de CPU e acionar automaticamente os eventos de escalabilidade.

---

# Política de Escalabilidade

A infraestrutura utiliza uma política de Target Tracking baseada em CPU:

* Meta de utilização de CPU: 50%
* Escalabilidade automática durante alta demanda
* Redução automática de recursos durante baixa utilização

---

# Arquitetura de Alta Disponibilidade

A solução foi implementada seguindo boas práticas da AWS:

* Distribuição em múltiplas Availability Zones
* Balanceamento de carga
* Redundância de instâncias
* Health checks automáticos
* Infraestrutura auto recuperável

---

# Conceitos Aprendidos

* Escalabilidade em nuvem
* Balanceamento de carga
* Tolerância a falhas
* Elasticidade de infraestrutura
* Monitoramento de recursos
* Alta disponibilidade
* Arquitetura AWS

---

# Habilidades Demonstradas

* Administração de instâncias EC2
* Configuração de Elastic Load Balancer
* Configuração de Auto Scaling
* Monitoramento com CloudWatch
* Redes na AWS
* Arquitetura de infraestrutura
* Deploy altamente disponível

---

# Resultado Final

Ao final do laboratório, a infraestrutura foi capaz de:

* Distribuir automaticamente o tráfego entre múltiplos servidores
* Escalar automaticamente conforme o uso da aplicação
* Substituir instâncias com falha automaticamente
* Garantir maior disponibilidade da aplicação

---

# Autor

Paulo Henrique
Estudante de Cloud Computing | Suporte de TI | Entusiasta de Infraestrutura AWS

---

