<h1 align="center">

[![image](https://github.com/user-attachments/assets/012db8db-ae41-4a8e-b510-89886de09a2d)](https://grafana.com/)

Script para Instalação do Grafana

</h1>

<h4 align="center">

Instruções para executar o script install_grafana.sh e o primeiro acesso à plataforma. 

</h4>

## Pré-Requisitos

Antes de executar o script, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Ubuntu e Debian
- **Mínimo de disco:** 16 GB
- **Mínimo de memória RAM:** 4 GB
- **Mínimo de CPU:** 2 CPU

<br>

## Execução do Script
**1. Atualizar o servidor**

Antes de executar o script, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Clone o repositório**

Clone o repositório onde o script de instalação está armazenado.
```bash
git clone https://github.com/VieiraSantosz/grafana-guide.git
```

**3. Navegar até o diretório do script**

Acesse a pasta onde o script foi clonado.
```bash
cd grafana-guide/script
```

**4. Conceder permissões para o script**

Antes de executar o script, é necessário garantir que ele tenha permissões de execução.
```bash
chmod +x install_grafana.sh
```

**5. Executar o script de instalação**

Agora, execute o script para iniciar a instalação do Grafana.
```bash
./install_grafana.sh
```

![image](https://github.com/user-attachments/assets/44874870-fff5-4227-be50-5dc94942cc40)


Após a instalação, o script fornecerá as credenciais para o primeiro acesso **(user e senha)** e o link de acesso à interface web. Guarde essas informações, pois você precisará delas para acessar a plataforma do Grafana.

![image](https://github.com/user-attachments/assets/e4ac592a-7cca-4df5-8a9c-1857dc85c528)

<br>

## Primeiro acesso à plataforma
**1. Acessar a interface web**

Abra o navegador e acesse a interface web do Grafana utilizando o IP da sua máquina seguido da porta 3000.
```bash
http://<IP-do-Servidor:3000>
```

**2. Login inicial**

Utilize as credenciais fornecidas durante a instalação para realizar o login na plataforma.

![image](https://github.com/user-attachments/assets/fa85656b-8335-4a6e-a53a-16b5514b56b6)

**3. Trocar a senha**

Por segurança, o Grafana exige que a senha padrão do usuário admin seja alterada logo após o primeiro login.

![image](https://github.com/user-attachments/assets/356056b6-8854-47cc-99be-6ca8de42c5f1)


**4. Após o Login**

Após a troca de senha, você será redirecionado para a interface principal do Grafana.

![image](https://github.com/user-attachments/assets/8388280c-41cf-42b7-90f3-ff09c2c37c2b)

<br>

## Solução de Problemas
Caso a instalação não tenha ocorrido conforme esperado, verifique o seguinte:

- **Falha na conexão com a internet:** Verifique se a sua conexão está funcionando corretamente e que o servidor pode acessar os repositórios do Grafana.
- **Acesso à interface web:** Se você não consegue acessar a interface web, verifique se a porta 3000 está aberta no firewall do servidor.
- **Serviço Grafana não está em execução:** Certifique-se de que o serviço está ativo.
