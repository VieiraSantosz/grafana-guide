<h1 align="center">

[![Wazuh Logo](https://github.com/user-attachments/assets/119abd64-9d52-4170-b976-6037f76f6097)](https://wazuh.com)

Script para Instalação do Wazuh

</h1>

<h4 align="center">

Instruções para executar o script install_wazuh.sh e o primeiro acesso à plataforma. 

</h4>

## Pré-Requisitos

Antes de executar o script, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Ubuntu 16.04, 18.04, 20.04, 22.04, 24.04
- **Mínimo de disco:** 50 GB
- **Mínimo de memória RAM:** 8 GB
- **Mínimo de CPU:** 4 CPU


## Execução do Script
**1. Atualizar o servidor**

Antes de executar o script, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Clone o repositório**

Clone o repositório onde o script de instalação está armazenado.
```bash
git clone https://github.com/VieiraSantosz/wazuh-guide.git
```

**3. Navegar até o diretório do script**

Acesse a pasta onde o script foi clonado.
```bash
cd wazuh-guide/script
```

**4. Conceder permissões para o script**

Antes de executar o script, é necessário garantir que ele tenha permissões de execução.
```bash
chmod +x install_wazuh.sh
```

**5. Executar o script de instalação**

Agora, execute o script para iniciar a instalação do Wazuh.
```bash
./install_wazuh.sh
```

![Wazuh](https://github.com/user-attachments/assets/53ae1d47-dc4c-4c9a-ab77-0f3c4762ee8b)


Após a instalação, o script fornecerá as credenciais para o primeiro acesso (login e senha) e o link de acesso à interface web. Guarde essas informações, pois você precisará delas para acessar a plataforma do Wazuh.

![image](https://github.com/user-attachments/assets/b4e94513-db92-4bfe-ab59-49c3584f115f)



## Primeiro acesso à plataforma
**1. Acessar a interface web**

Após a instalação, abra o seu navegador e insira link de acesso à interface web, que foi fornecido pelo script, para acessar a plataforma do Wazuh:
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

Caso encontre problemas durante o processo de instalação ou ao acessar a plataforma, aqui estão algumas dicas para resolver:

- Problema com a conexão à internet: Verifique se o servidor está conectado à internet e consegue acessar os repositórios do Wazuh.
- Erro ao executar o script: Caso o script não execute corretamente, consulte o log de instalação para mais detalhes sobre o erro. O log pode ser encontrado em **/var/log/wazuh-install.log**.
- Acesso à interface web: Se não conseguir acessar a interface web, verifique se a porta 443 (HTTPS) está aberta no firewall do servidor.
