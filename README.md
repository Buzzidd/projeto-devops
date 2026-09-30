# Projeto Integrador — Cloud & DevOps

Este repositório contém a infraestrutura como código e a aplicação desenvolvida para a disciplina de Cloud Computing e DevOps.

## Integrantes

- Carlos Vitor Camara Gomes
- Joaquim Camillo Pereira Neto
- Giovanna Secundo Penso
- Lucas Gabriel Barreto Oliveira
- Ricardo Amorin Machado Junior
- Carlos Eduardo Passos Silva
- Agnaldo Santos Silva Júnior
- Eduardo Micael Saraiva Maia
- Artur Oliveira Ximenes De Almeida
- Guilherme Cavalcante Bandeira

## 1. Descrição da aplicação

A aplicação consiste num site estático em HTML servido através de um servidor web configurado em containers. O objetivo é demonstrar a implementação de uma esteira completa de DevOps, desde a hospedagem na cloud até ao monitoramento contínuo.

## 2. Arquitetura do ambiente

O ambiente foi construído utilizando os seguintes recursos:

- **Provedor Cloud:** AWS (Amazon Web Services).
- **Servidor:** Instância EC2 (t3.micro) com sistema operativo Ubuntu.
- **Rede:** IP Público fixo (18.191.162.150) com Security Groups configurados para permitir tráfego HTTP (80), HTTPS (443) e porta personalizada para monitoramento (3001).

## 3. Tecnologias utilizadas

- HTML
- AWS (EC2 e Security Groups)
- Docker & Docker Compose
- GitHub Actions (CI/CD automatizado)
- Uptime Kuma (Monitoramento)
- Git e GitHub

## 4. Estrutura do projeto

```text
projeto-devops/
├── .github/workflows/
│   └── deploy.yml          # Pipeline de CI/CD
├── docker-compose.yml      # Orquestração dos containers
├── Dockerfile              # Construção da imagem da aplicação web
├── index.html              # Código-fonte da aplicação
└── README.md               # Documentação do projeto
```
