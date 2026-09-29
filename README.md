# Trabalho N1 - DevOps e Computação em Nuvem

## Integrantes

- Cauan Alexandre Medeiros Pontes
- PEDRO HENRIQUE CORREIA DE OLIVEIRA
- RUAN MOREIRA FERREIRA
- JÓSIMO RONNYER AMARAL MARTINS
- CAUA FERREIRA SALES SILVA

## Disciplina

DevOps e Computação em Nuvem

---

# 1. Link do Repositório Git

Repositório Público:

```text
https://github.com/c4uxns/trabalho-castelo
```

---

# 2. URL da Aplicação

Aplicação publicada na internet:

```text
https://www.genghiskhan.space
```

IP público do servidor:

```text
144.22.162.133:5000
```

---

# 3. Descrição da Aplicação

A aplicação consiste em uma página web simples desenvolvida para a disciplina de DevOps e Computação em Nuvem.

A página apresenta:

- Nome da disciplina;
- Nome completo dos integrantes do grupo;
- Aplicação acessível através de HTTP e HTTPS;
- Hospedagem em ambiente cloud utilizando Oracle Cloud.

---

# 4. Ambiente Cloud

## Provedor Utilizado

Oracle Cloud Infrastructure (OCI)

## Sistema Operacional

Ubuntu Linux

## Recursos da Máquina

| Recurso | Configuração |
|----------|------------|
| CPU | 1 OCPU |
| Memória | 6 GB RAM |

## Endereço IP

```text
144.22.162.133
```

## Portas Utilizadas

| Porta | Serviço |
|---------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 5000 | Aplicação Flask |

## Forma de Acesso

A administração do servidor é realizada através de SSH:

```bash
ssh usuario@144.22.162.133
```

---

# 5. Arquitetura do Ambiente

Fluxo de funcionamento da aplicação:

```text
Usuário
   │
   ▼
www.genghiskhan.space
   │
   ▼
DNS
   │
   ▼
IP Público (144.22.162.133)
   │
   ▼
Servidor Oracle Cloud
   │
   ▼
Nginx
   │
   ▼
Container Docker
   │
   ▼
Aplicação Flask
```

Diagrama Simplificado:

```text
┌──────────────┐
│   Usuário   │
└──────┬──────┘
       │ HTTPS
       ▼
┌────────────────────┐
│ genghiskhan.space  │
└──────┬─────────────┘
       │ DNS
       ▼
┌────────────────────┐
│ Oracle Cloud       │
│ Ubuntu Linux       │
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ Nginx Reverse Proxy│
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ Docker Container   │
│ Aplicação Flask    │
└────────────────────┘
```

---

# 6. Tecnologias Utilizadas

- Python
- Flask
- Docker
- Docker Compose
- Nginx
- Git
- GitHub
- GitHub Actions
- Oracle Cloud
- Ubuntu Linux
- HTTPS/SSL

---

# 7. Estrutura do Projeto

```text
trabalho-castelo/
│
├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── templates/
│   └── index.html
│
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── README.md
└── .gitignore
```

## Descrição dos Arquivos

### app.py

Arquivo principal da aplicação Flask.

### templates/index.html

Página HTML exibida aos usuários.

### requirements.txt

Dependências do projeto.

### Dockerfile

Arquivo responsável pela criação da imagem Docker.

### docker-compose.yml

Arquivo responsável pela execução dos containers.

### deploy.yml

Pipeline de CI/CD via GitHub Actions.

### README.md

Documentação do projeto.

---

# 8. Processo de Instalação

## Clonar o Repositório

```bash
git clone https://github.com/c4uxns/trabalho-castelo.git
```

## Acessar o Diretório

```bash
cd trabalho-castelo
```

## Construir a Imagem Docker

```bash
docker build -t trabalho-castelo .
```

## Iniciar os Containers

```bash
docker compose up -d
```

## Verificar Containers

```bash
docker ps
```

## Acessar Aplicação

```text
http://localhost:5000
```

---

# 9. Processo de Deploy

O deploy é realizado através da pipeline configurada no GitHub Actions.

Fluxo:

```text
Desenvolvedor
      │
      ▼
Git Push
      │
      ▼
GitHub
      │
      ▼
GitHub Actions
      │
      ▼
Servidor Oracle Cloud
      │
      ▼
Nova Versão da Aplicação
```

---

# 10. Configuração do Docker

O projeto utiliza Docker para garantir portabilidade e facilidade de implantação.

## Dockerfile

Responsável por:

- Criar imagem baseada em Python;
- Copiar os arquivos da aplicação;
- Instalar dependências;
- Iniciar a aplicação Flask.

## Docker Compose

Responsável por:

- Gerenciar containers;
- Configurar portas;
- Facilitar atualização da aplicação.

Fluxo Docker:

```text
Código
  │
  ▼
Imagem Docker
  │
  ▼
Container
  │
  ▼
Aplicação
```

---

# 11. Configuração do DNS

Domínio configurado:

```text
www.genghiskhan.space
```

Fluxo DNS:

```text
Domínio
   │
   ▼
DNS
   │
   ▼
IP 144.22.162.133
   │
   ▼
Servidor Oracle Cloud
   │
   ▼
Aplicação
```

O DNS é responsável por direcionar o domínio para o endereço IP público do servidor.

---

# 12. Configuração do HTTPS

O acesso à aplicação é realizado utilizando HTTPS.

Portas utilizadas:

```text
80  → HTTP
443 → HTTPS
```

Benefícios:

- Comunicação criptografada;
- Maior segurança;
- Proteção contra interceptação de dados;
- Autenticidade do servidor.

Fluxo:

```text
Usuário
   │
   ▼
HTTPS
   │
   ▼
Certificado SSL/TLS
   │
   ▼
Servidor
   │
   ▼
Aplicação
```

---

# 13. Processo de CI/CD

A automação é realizada através do GitHub Actions.

Fluxo implementado:

```text
Git Push
   │
   ▼
Build
   │
   ▼
Validação
   │
   ▼
Deploy
   │
   ▼
Produção
```

Benefícios:

- Automatização do deploy;
- Redução de erros humanos;
- Maior velocidade de entrega;
- Padronização do ambiente.

---

# 14. Monitoramento

O monitoramento do ambiente permite verificar a disponibilidade da aplicação e da infraestrutura.

Verificações realizadas:

### Aplicação Online

```text
https://www.genghiskhan.space
```

### Servidor Online

```bash
ping 144.22.162.133
```

### Container Online

```bash
docker ps
```

### Logs da Aplicação

```bash
docker logs <container_id>
```

Indicadores monitorados:

- Disponibilidade do site;
- Disponibilidade do servidor;
- Status do container;
- Resposta HTTP/HTTPS.

---

# 15. Procedimentos Básicos de Recuperação

## Verificar Containers

```bash
docker ps
```

## Reiniciar Serviço

```bash
docker compose restart
```

## Recriar Containers

```bash
docker compose down
docker compose up -d --build
```

## Verificar Logs

```bash
docker logs <container_id>
```

## Verificar Portas

```bash
sudo ss -tulnp
```

## Reiniciar Servidor

```bash
sudo reboot
```

---

# Evidências da Entrega

Adicionar capturas de tela das seguintes evidências:

## Evidência do Ambiente Cloud

- Instância Oracle Cloud criada;
- <img width="1567" height="96" alt="image" src="https://github.com/user-attachments/assets/470d92a8-b92e-495a-8649-3dbcf19f4e08" />


- Informações da VM;
- <img width="1415" height="766" alt="trabalho" src="https://github.com/user-attachments/assets/6704e859-68a5-4a10-8fe3-6c989dab9100" />

- Endereço IP público.
- http://144.22.162.133:5000

## Evidência do Docker

- Resultado do comando:

```bash
docker ps
```
<img width="651" height="45" alt="image" src="https://github.com/user-attachments/assets/635f80c9-909b-4b9a-967b-d979331099c6" />


- Imagem Docker criada:

```bash
docker images
```
<img width="729" height="116" alt="image" src="https://github.com/user-attachments/assets/71bd8beb-b566-4d77-ab93-291f0d58c680" />



## Evidência do CI/CD

- Execução da pipeline no GitHub Actions;
- <img width="1631" height="647" alt="image" src="https://github.com/user-attachments/assets/62a293a6-e1da-40f7-9de7-db08c5c8ff35" />

- Deploy realizado com sucesso.
- <img width="662" height="675" alt="image" src="https://github.com/user-attachments/assets/185f6bf2-0327-4f0b-9681-a99df926b271" />


## Evidência do Monitoramento

- Página de monitoramento;
- <img width="1894" height="442" alt="image" src="https://github.com/user-attachments/assets/68f82507-5885-4f1f-91e2-6aae16f77744" />

- Verificação da disponibilidade da aplicação;
- Status do servidor e dos containers.
<img width="1872" height="904" alt="image" src="https://github.com/user-attachments/assets/d3894d97-8445-46d1-8c57-e554d7dcb687" />


## Evidência da Aplicação

- Página inicial carregada;
- <img width="1920" height="1043" alt="image" src="https://github.com/user-attachments/assets/8097d002-50da-4afa-a33b-587b0f1bbca0" />

- Domínio funcionando;
- HTTPS ativo com certificado válido.
- <img width="316" height="271" alt="image" src="https://github.com/user-attachments/assets/46841603-be1c-4a1c-bccc-468d1d12b6ec" />

