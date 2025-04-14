<h1 align="center">

![image](https://github.com/user-attachments/assets/012db8db-ae41-4a8e-b510-89886de09a2d)

Guia de Instalação do Grafana

</h1>

<h4 align="center">

Instruções para a instalação do Wazuh e o primeiro acesso à plataforma.

</h4>

## Pré-Requisitos

Antes de iniciar a instalação, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** CentOS, Red Hat Enterprise Linux (RHEL), Ubuntu e Amazon Linux
- **Mínimo de disco:** 50 GB
- **Mínimo de memória RAM:** 8 GB
- **Mínimo de CPU:** 4 CPU


## Instalação do Wazuh

**1. Atualizar o servidor**

Antes de iniciar a instalação, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Baixar e executar o assistente de instalação do Wazuh**

Este script automatiza a instalação e configuração do Wazuh. Durante o processo, o assistente irá configurar o servidor Wazuh, baixar os pacotes necessários e configurar o ambiente para você.
```bash
curl -sO https://packages.wazuh.com/4.11/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

Após a instalação, o assistente do Wazuh fornecerá as credenciais para o primeiro acesso (login e senha). Guarde essas informações, pois você precisará delas para acessar a interface web do Wazuh.

![Acesso Wazuh](https://github.com/user-attachments/assets/3297659a-f968-499d-af37-ce7f5d7a0eb4)


## Primeiro acesso à plataforma
**1. Acessar a interface web**

Após a instalação, abra o seu navegador e insira a seguinte URL para acessar a plataforma do Wazuh:
```bash
https://<IP-do-Servidor>
```
**Nota:** Caso você esteja acessando a plataforma remotamente, substitua o **localhost** pelo endereço IP ou nome de domínio do servidor onde o Wazuh foi instalado.

**2. Login inicial**

Utilize as credenciais fornecidas durante a instalação para realizar o login na plataforma.

![Wazuh](https://github.com/user-attachments/assets/88f1c874-f404-4094-8000-e29f428a8926)

**3. Após o Login**

Depois de realizar o login, você estará pronto para começar a explorar e configurar a plataforma Wazuh.

![image](https://github.com/user-attachments/assets/83deff03-05c0-4a5b-8aea-756dbac1c52e)


## Solução de Problemas
Caso a instalação não tenha ocorrido conforme esperado, verifique o seguinte:

- **Falha na conexão com a internet:** Verifique se a sua conexão está funcionando corretamente e que o servidor pode acessar os repositórios do Wazuh.
- **Erros durante o script de instalação:** Se o script falhou, consulte o log de instalação para mensagens de erro detalhadas. O log pode ser encontrado em **/var/log/wazuh-install.log.**
- **Acesso à interface web:** Se você não consegue acessar a interface web, verifique se a porta 443 está aberta no firewall do servidor.
   
 



