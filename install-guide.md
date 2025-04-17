<h1 align="center">

[![image](https://github.com/user-attachments/assets/012db8db-ae41-4a8e-b510-89886de09a2d)](https://grafana.com/)

Guia de Instalação do Grafana

</h1>

<h4 align="center">

Instruções para a instalação do Grafana e o primeiro acesso à plataforma.

</h4>

## Pré-Requisitos

Antes de iniciar a instalação, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Red Hat Enterprise Linux (RHEL), Fedora, Ubuntu e Debian
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

Esses pacotes são necessários para permitir que o sistema adicione repositórios externos, baixe arquivos via HTTPS e manipule chaves GPG com segurança.
```bash
sudo apt-get install -y apt-transport-https software-properties-common wget
```

**3. Importar a chave GPG**

O Grafana fornece uma chave GPG para garantir a autenticidade e a integridade dos pacotes. Esse passo adiciona essa chave ao seu sistema, para que os pacotes do Grafana possam ser verificados.
```bash
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

**4. Adicionar um repositório para versões estáveis**

Com a chave importada, agora é possível adicionar o repositório do Grafana ao sistema para instalar os pacotes diretamente da fonte oficial.
```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

**5. Atualizar a lista de pacotes disponíveis**

Agora que o repositório do Grafana foi adicionado, você precisa atualizar novamente os índices de pacotes para que o APT reconheça os pacotes disponíveis a partir do novo repositório.
```bash
sudo apt-get update && apt-get upgrade -y
```

**6. Instalar o Grafana OSS ou Entreprise**

Agora que todos os pré-requisitos estão configurados corretamente, você pode escolher qual versão do Grafana deseja instalar, dependendo das suas necessidades. O Grafana oferece duas versões principais:

- **Grafana OSS (Open-Source Software):** Esta é a versão gratuita e de código aberto do Grafana. Ela inclui a maioria dos recursos essenciais, como dashboards, alertas, plugins, e integrações com várias fontes de dados. É ideal para a maioria dos usuários que não precisam de funcionalidades avançadas oferecidas pela versão Enterprise.

```bash
sudo apt-get install grafana -y
```

- **Grafana Enterprise:** Esta versão é destinada a usuários que necessitam de recursos adicionais voltados para ambientes corporativos, como suporte avançado, segurança aprimorada, recursos de escalabilidade, integrações mais avançadas com soluções de terceiros e plugins premium. Ela é licenciada e requer uma chave de licença.

```bash
sudo apt-get install grafana-enterprise -y
```

Se você não tem certeza de qual versão escolher, a versão **OSS** é uma boa opção de início, pois oferece todos os recursos principais do Grafana, e você pode sempre migrar para a versão Enterprise mais tarde, se necessário.

## Iniciar e habilitar o serviço Grafana

**1. Iniciar os serviços**

Depois da instalação, é necessário iniciar o serviço do Grafana e garantir que ele seja iniciado automaticamente junto com o sistema operacional.
```bash
sudo systemctl daemon-reload
sudo systemctl start grafana-server
```

**2. Configurar o servidor Grafana para iniciar na inicialização**

Ativar o serviço do Grafana para que ele seja iniciado automaticamente ao ligar ou reiniciar o servidor.
```bash
sudo systemctl enable grafana-server.service
```

![image](https://github.com/user-attachments/assets/a23bbd1d-7f2e-4a15-87f3-3064cba765b7)

**3. Verificar se o serviço está sendo executado**

Verificar se o serviço está **active (running)** ou se ocorreu algum erro.
```bash
sudo systemctl status grafana-server
```

![image](https://github.com/user-attachments/assets/7d6ac3b6-c8b6-4001-a7cd-c9c32473f744)

**Nota:** Se o serviço estiver em execução corretamente, você verá uma mensagem indicando que ele está ativo. Caso contrário, revise os passos anteriores.


## Primeiro acesso à plataforma

**1. Acessar a interface web**

Abra o navegador e acesse a interface web do Grafana utilizando o IP da sua máquina seguido da porta 3000.
```bash
http://<IP-do-Servidor:3000>
```

**2. Login inicial**

Ao acessar pela primeira vez, você verá a tela de login do Grafana. Use as credenciais padrão para acessar:

**Usuário:** admin

**Senha:** admin

![image](https://github.com/user-attachments/assets/fa85656b-8335-4a6e-a53a-16b5514b56b6)

**3. Trocar a senha**

Por segurança, o Grafana exige que a senha padrão do usuário admin seja alterada logo após o primeiro login.

![image](https://github.com/user-attachments/assets/356056b6-8854-47cc-99be-6ca8de42c5f1)


**4. Após o Login**

Assim que a senha for atualizada, o sistema redirecionará você para a interface principal do Grafana.

![image](https://github.com/user-attachments/assets/8388280c-41cf-42b7-90f3-ff09c2c37c2b)


## Solução de Problemas
Caso a instalação não tenha ocorrido conforme esperado, verifique o seguinte:

- **Falha na conexão com a internet:** Verifique se a sua conexão está funcionando corretamente e que o servidor pode acessar os repositórios do Grafana.
- **Acesso à interface web:** Se você não consegue acessar a interface web, verifique se a porta 3000 está aberta no firewall do servidor.
- **Serviço Grafana não está em execução:** Certifique-se de que o serviço está ativo.

