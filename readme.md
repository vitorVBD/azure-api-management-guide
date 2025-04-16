<p align="center">
<img src="./assets/azure-logo.png" alt="Azure API Management" width="150" /> <br /> <b>Guia para Configuração de APIs com API Management no Azure</b> <br /> <sub><sup><b>(azure-api-management-guide)</b></sup></sub> <br /> </p> 
<p align="center"> Este projeto é um guia detalhado para configurar e gerenciar APIs utilizando o Azure API Management (APIM). Ele abrange desde a criação do APIM até a configuração de autenticação com JWT, boas práticas e monitoramento. <br /> </p>

<p align="center"> This project is a detailed guide for configuring and managing APIs using Azure API Management (APIM). It covers everything from creating the APIM to setting up JWT authentication, best practices, and monitoring. <br /> </p

---
<details> <summary>🇧🇷 Detalhes do Projeto (Português)</summary>

## Resumo do Projeto

Este guia foi desenvolvido para auxiliar na configuração de APIs no Azure utilizando o API Management. Ele fornece instruções passo a passo para criar, configurar e gerenciar APIs, incluindo práticas recomendadas e configurações avançadas, como autenticação com JWT.

---

## Funcionalidades

- **Criação do API Management (APIM)**: Instruções para configurar o APIM, incluindo escolha de região, grupo de recursos e camada de preços.
- **Monitoramento**: Configuração de Log Analytics e Defender for Cloud para monitorar e proteger as APIs.
- **Configuração de Rede**: Orientações para configurar redes virtuais (VNET) ou endpoints privados.
- **Autenticação com JWT**: Passo a passo para configurar autenticação segura utilizando tokens JWT.
- **Boas Práticas**: Recomendações para ajustar endereços HTTP, configurar assinaturas e gerenciar permissões.
- **Configuração de CORS**: Controle de acesso às APIs por meio de configurações de CORS.

---

## Tecnologias e Ferramentas Utilizadas

- **Azure API Management (APIM)**: Serviço de gerenciamento de APIs.
- **Log Analytics**: Ferramenta para monitoramento e análise de logs.
- **Defender for Cloud**: Solução de segurança para proteger recursos no Azure.
- **JWT (JSON Web Token)**: Padrão para autenticação segura.

---

# Guia para Configuração de uma API com API Management no Azure

## 1. Criando o API Management (APIM)

1. Escolha a **região**.
2. Defina o **grupo de recursos**, **e-mail** e o **nome da organização**.
3. Escolha a **camada (Pricing Tier)**:
   - Avalie a camada que melhor atende às necessidades do negócio.
   - Consulte a documentação oficial para mais detalhes sobre os preços.

## 2. Monitoramento

- Configure o **Log Analytics** para monitorar a API.
- Utilize o **Defender for Cloud** para aumentar a segurança.

## 3. Configuração de Rede (Virtual Network)

- Caso utilize **VNET**, escolha a **Virtual Network** e as **sub-redes**.
- Caso contrário, configure um **private endpoint**.

## 4. Identidade Gerenciada

- Defina se o recurso terá acesso a outros recursos existentes no Azure.

## 5. Tags

- Utilize **tags** para identificar quem está usando e monitorar os custos do projeto.

## 6. Configuração de CORS

- Configure o **CORS** para controlar o acesso à API.
- Adicione o endereço do APIM.

## 7. Configurando a API

1. Adicione uma nova API.
2. Escolha o **App Service**.
3. Defina:
   - Nome da API.
   - Sufixo da URL.
4. Crie:
   - Tags.
   - Produtos.
   - Versões da API (se necessário).
5. Finalize criando a API.

## 8. Boas Práticas

- Na aba **Design**, ajuste os endereços das requisições HTTP.
- Em **Settings**, configure a assinatura (Subscription):
  - Altere o nome do cabeçalho (Header name), geralmente começando com `x-`, ex.: `x-api-key`.
- Em **Subscriptions**, crie uma nova assinatura:
  - Defina o nome.
  - Escolha a API criada.
  - Gere a chave de acesso.

## 9. Configurando Autenticação com JWT

1. No **App Registration**, registre um novo aplicativo:
   - Salve o **Client ID**, **OAUTH Token Endpoint** e **OpenID**.
   - Em **Manage -> Certificates & Secrets**, crie uma nova secret e salve o valor.
   - Se necessário, crie roles e adicione permissões.
2. Configure a validação do JWT no APIM:
   - Valide o token no cabeçalho (Header).
   - Defina o nome do cabeçalho e mensagens de erro.
   - Em **Issuers**, cole o `aud` e `iss` do token.
3. No **App Registration**, em **Expose an API**, adicione um escopo (scope).
4. Na API, configure:
   - Adicione o `aud` do token em **Audiences**.
   - Cole o **OpenID URL**.

---
Este guia fornece uma visão geral para configurar e gerenciar APIs no Azure utilizando o API Management. Certifique-se de consultar a documentação oficial para detalhes adicionais.

---

</details>

<details> <summary>🇺🇸 Project Details (English)</summary>

## Project Summary

This guide was developed to assist in configuring APIs on Azure using API Management. It provides step-by-step instructions for creating, configuring, and managing APIs, including best practices and advanced configurations such as JWT authentication.

---

## Features

- **API Management (APIM) Creation**: Instructions for setting up APIM, including region selection, resource group, and pricing tier.
- **Monitoring**: Setup of Log Analytics and Defender for Cloud to monitor and secure the APIs.
- **Network Configuration**: Guidance for setting up Virtual Networks (VNET) or private endpoints.
- **JWT Authentication**: Step-by-step guide for configuring secure authentication using JWT tokens.
- **Best Practices**: Recommendations for adjusting HTTP addresses, configuring subscriptions, and managing permissions.
- **CORS Configuration**: Control API access through CORS settings.

---

## Technologies and Tools Used

- **Azure API Management (APIM)**: API management service.
- **Log Analytics**: Tool for monitoring and analyzing logs.
- **Defender for Cloud**: Security solution to protect Azure resources.
- **JWT (JSON Web Token)**: Standard for secure authentication.

---

# Guide to Configuring an API with API Management on Azure

## 1. Creating API Management (APIM)

1. Choose the **region**.
2. Set the **resource group**, **email**, and **organization name**.
3. Choose the **Pricing Tier**:
   - Evaluate the tier that best suits the business needs.
   - Refer to the official documentation for pricing details.

## 2. Monitoring

- Configure **Log Analytics** to monitor the API.
- Use **Defender for Cloud** to enhance security.

## 3. Network Configuration (Virtual Network)

- If using **VNET**, select the **Virtual Network** and **subnets**.
- Otherwise, configure a **private endpoint**.

## 4. Managed Identity

- Define whether the resource will access other existing resources on Azure.

## 5. Tags

- Use **tags** to identify who is using the resource and to monitor project costs.

## 6. CORS Configuration

- Configure **CORS** to control API access.
- Add the APIM address.

## 7. Configuring the API

1. Add a new API.
2. Choose the **App Service**.
3. Define:
   - API name.
   - URL suffix.
4. Create:
   - Tags.
   - Products.
   - API versions (if needed).
5. Finalize by creating the API.

## 8. Best Practices

- In the **Design** tab, adjust HTTP request addresses.
- In **Settings**, configure the subscription:
  - Change the header name, usually starting with `x-`, e.g., `x-api-key`.
- In **Subscriptions**, create a new subscription:
  - Define the name.
  - Select the created API.
  - Generate the access key.

## 9. Configuring JWT Authentication

1. In **App Registration**, register a new application:
   - Save the **Client ID**, **OAUTH Token Endpoint**, and **OpenID**.
   - In **Manage -> Certificates & Secrets**, create a new secret and save the value.
   - If necessary, create roles and add permissions.
2. Configure JWT validation in APIM:
   - Validate the token in the **header**.
   - Set the header name and error messages.
   - In **Issuers**, paste the token’s `aud` and `iss`.
3. In **App Registration**, go to **Expose an API** and add a scope.
4. In the API, configure:
   - Add the token `aud` in **Audiences**.
   - Paste the **OpenID URL**.

---

This guide provides an overview of how to configure and manage APIs on Azure using API Management. Be sure to check the official documentation for additional details.

---

</details>

---

## License

This software is licensed under the terms of the **MIT License**.

---

<div align="center">

Developed by [Vitor Bittencourt](https://linktr.ee/vv_bittencourt) ☕

</div>