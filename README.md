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
- Informações da VM;
- Endereço IP público.

## Evidência do Docker

- Resultado do comando:

```bash
docker ps
```

- Imagem Docker criada:

```bash
docker images
```

## Evidência do CI/CD

- Execução da pipeline no GitHub Actions;
- Deploy realizado com sucesso.

## Evidência do Monitoramento

- Página de monitoramento;
- Verificação da disponibilidade da aplicação;
- Status do servidor e dos containers.

## Evidência da Aplicação

- Página inicial carregada;
- Domínio funcionando;
- HTTPS ativo com certificado válido.
