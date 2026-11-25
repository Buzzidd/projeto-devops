
# Execução local e troubleshooting

## 1. Pré-requisitos

- Windows com Docker Desktop instalado.
- Docker Engine em execução.
- Git instalado.
- Repositório clonado localmente.

## 2. Inicialização do ambiente

Entre na pasta do projeto:

```bash
cd projeto-devops
```

Crie a rede externa de observabilidade, caso ainda não exista:

```bash
docker network create obs
```

Inicie os containers:

```bash
docker compose up -d --build
```

Verifique os serviços:

```bash
docker compose ps
```

## 3. Acesso às interfaces

- Aplicação CloudOps: http://127.0.0.1
- Grafana: http://127.0.0.1:3000

No ambiente Windows utilizado durante os testes, o acesso por `localhost` apresentou timeout quando o Curl tentou utilizar IPv6 (`::1`).

Ao forçar IPv4, a aplicação respondeu corretamente com HTTP 200 OK:

```powershell
curl.exe -4 -I http://127.0.0.1/
```

A causa específica do comportamento em IPv6 permaneceu em investigação.

## 4. Diagnóstico da aplicação

Verificar o NGINX dentro do container:

```bash
docker compose exec web sh -c "wget -S -O- -T 5 http://127.0.0.1/"
```

Verificar a comunicação entre Caddy e NGINX:

```bash
docker compose exec caddy sh -c "wget -S -O- -T 5 http://site_devops:80/"
```

Verificar os logs:

```bash
docker compose logs --tail=50
```

## 5. Encerramento

Para parar os serviços:

```bash
docker compose down
```

Para iniciar novamente:

```bash
docker compose up -d
```

---

Documentação baseada nos testes de execução local e
diagnóstico realizados com Docker Desktop no Windows.
    