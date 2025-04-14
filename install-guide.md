<h1 align="center">

[![image](https://github.com/user-attachments/assets/012db8db-ae41-4a8e-b510-89886de09a2d)](https://grafana.com/)

Guia de Instalação do Grafana

</h1>

<h4 align="center">

Instruções para a instalação do Grafana e o primeiro acesso à plataforma.

</h4>

## Pré-Requisitos

Antes de iniciar a instalação, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Red Hat Enterprise Linux (RHEL), Fedroa, Ubuntu e Debian
- **Mínimo de disco:** 16 GB
- **Mínimo de memória RAM:** 4 GB
- **Mínimo de CPU:** 2 CPU


## Instalação do Grafana

**1. Atualizar o servidor**

Antes de iniciar a instalação, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Instalar os pacotes de pré-requisitos**

```bash
sudo apt-get install -y apt-transport-https software-properties-common wget
```

**3. Importar a chave GPG**

```bash
sudo mkdir -p /etc/apt/keyrings/
```

```bash
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

**4. Adicionar um repositório para versões estáveis**

```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

**5. Atualizar a lista de pacotes disponíveis**

```bash
sudo apt-get update && apt-get upgrade -y
```

**6. Instalar o Grafana OSS**

```bash
sudo apt-get install grafana -y
```

**7. Instalar o Grafana Enterprise**

```bash
sudo apt-get install grafana-enterprise -y
```

## Iniciar o servidor Grafana

**1. Iniciar os serviços**

```bash
sudo systemctl daemon-reload
```

```bash
sudo systemctl start grafana-server
```

**2. Configurar o servidor Grafana para iniciar na inicialização**

```bash
sudo systemctl enable grafana-server.service
```








