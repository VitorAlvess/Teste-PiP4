# P1P4 Bot

Uma automação que visa facilitar e acelerar o processo de candidatura e recepção de novos voluntários para [opipa.org](https://opipa.org)

## Visão Geral

O **P1P4** desempenha a tarefa de coletar informações de novos voluntários que se cadastraram nas vagas de voluntariado pelo site *atados.com.br*. Usando técnicas de web scraping, ele extrai os dados pertinentes. A integração da API do Google Sheets permite a inserção desses dados em uma planilha do Google. Esta planilha é então utilizada como hub central para a gestão dos novos voluntários.

À medida que a planilha é preenchida, ocorre a organização das informações e o acompanhamento do progresso de cada candidato. Com base nesse gerenciamento, o sistema automatizado dispara ações específicas. Dependendo da etapa em que o candidato se encontra, o **P1P4** envia e-mails ou mensagens pelo WhatsApp. Esse processo de automação garante que cada voluntário receba as orientações corretas e seja conduzido através do processo de inscrição de maneira eficiente e eficaz.

# Utilização

## Ferramentas utilizadas

- Python
    - Selenium
    - webdriver-manager
    - xlrd
    - google-api-python-client google-auth-httplib2 google-auth-oauthlib
- Javascript
    - NodeJS
    - nodemailer
    - googleapis@105 @google-cloud/local-auth@2.1.0
    - whatsapp-web.js
    - qrcode-terminal

## Instalação

O P1P4 é divido em 3 arquivos que funcionam de maneira independentemente porém suas ações são dependentes uma das outras.

### 1°- Atados/selenium

1. Instalação do Python
2. Instalação das bibliotecas
    - Selenium ( Biblioteca que controla o navegador)
    
    ```jsx
    pip install selenium
    ```
    
    - webdriver-manager ( Biblioteca que fiscaliza e atualiza o navegador usado )
    
    ```jsx
    pip install webdriver-manager
    ```
    
    - Webdriver
        - já vai ser baixado automática por causa do manager
        - sem o manager tem que instalar manualmente e colocar na pasta do projeto
    - xlrd para ler os arquivos no formato xls
    
    ```jsx
    pip install xlrd
    ```
    
    Subir dados para o google contacts:
    
    - Usar a API People do Google
        1. Acesse o console de desenvolvedor do Google em **[https://console.developers.google.com/](https://console.developers.google.com/)**.
        2. Crie um novo projeto ou selecione um projeto existente.
        3. Clique em "Habilitar APIs e Serviços".
        4. Busque por "People API" e selecione a opção "People API".
        5. Clique em "Habilitar".
            - Só preciso ativar ela pois já tenho as credenciais no código pois já usei uma API
            - Renomear o token para outro nome para não dar conflito com o token que pertence ao Google Sheets e possui o nome de token.json
    - Instalar a biblioteca da API do [Google Sheets](https://github.com/VitorAlvess/Automacao-KolibriStudio/blob/main/console.cloud.google.com/apis/api/sheets.googleapis.com)
    
    ```
    pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
    ```
    
    - Precisa criar credenciais no Google console ou reutilizar as que já existem.
    
    ```
    Console -> APIs e serviços -> Credenciais
    ```
    
    - Baixar as credenciais em JSON e inserir na pasta do projeto com o nome de token.json
    
    ## Como executar?
    
    ```
    cd Selenium
    python index.py
    ```
    
    ### 2°- Sheets-WhatsApp
    
    1. Instalação do NodeJS
    2. Criação de credencias e ativação da API google Drive e Google Sheets
    - Precisa criar credenciais no Google console ou reutilizar as que já existem.
    
    ```
    Console -> APIs e serviços -> Credenciais
    ```
    
3. Instalação das bibliotecas
    1. Nodemailer
        1. Biblioteca responsável pelo envio de e-mails
        
        ```
        npm install nodemailer
        ```
        
    2. Google Sheets API ( Contando com a criação das credenciais )
    
    ```
    npm install googleapis@105 @google-cloud/local-auth@2.1.0 --save
    ```
    
    c. ****whatsapp-web.js****
    
    ```
    npm i whatsapp-web.js
    npm i qrcode-terminal
    ```
    
    ## Como executar?
    
    ```
    cd Sheets-WhatsApp
    node index.js
    ```
    

### 3°- Automacao-Autentique

1. Instalação do Python
2. Instalação das bibliotecas
    - Selenium ( Biblioteca que controla o navegador)
    
    ```jsx
    pip install selenium
    ```
    
    - webdriver-manager ( Biblioteca que fiscaliza e atualiza o navegador usado )
    
    ```jsx
    pip install webdriver-manager
    ```
    
    - Webdriver
        - já vai ser baixado automática por causa do manager
        - sem o manager tem que instalar manualmente e colocar na pasta do projeto
    - Instalar a biblioteca da API do [Google Sheets](https://github.com/VitorAlvess/Automacao-KolibriStudio/blob/main/console.cloud.google.com/apis/api/sheets.googleapis.com)
    
    ```
    pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
    ```
    
    - Precisa criar credenciais no Google console ou reutilizar as que já existem.
    
    ```
    Console -> APIs e serviços -> Credenciais
    ```
    
    - Baixar as credenciais em JSON e inserir na pasta do projeto com o nome de token.json
    
    ## Como executar?
    
    ```
    cd Automacao-Autentique
    python index.py
    ```
    

## Licença

Mantido por José Victor Santos Alves

**Livre para usar e adaptar!**
