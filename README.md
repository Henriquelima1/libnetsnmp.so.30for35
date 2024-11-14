# Projeto de Linkagem de Bibliotecas SNMP para .deb

Este projeto cria um pacote `.deb` que estabelece linkagens simbólicas para as bibliotecas `libnetsnmpagent.so` e `libnetsnmp.so`, direcionando as versões 30 para as versões 35. Esse pacote é útil em sistemas onde aplicativos que dependem das versões 30 dessas bibliotecas precisam ser compatíveis com as versões 35.

## Objetivo

O objetivo deste projeto é fornecer um pacote `.deb` que automatize a criação de links simbólicos, permitindo que os binários e aplicativos que dependem das bibliotecas `libnetsnmpagent.so.30` e `libnetsnmp.so.30` utilizem as versões mais recentes (`libnetsnmpagent.so.35` e `libnetsnmp.so.35`) sem a necessidade de recompilar esses aplicativos.

## Linkagens Criadas

Ao instalar este pacote, os seguintes links simbólicos serão criados:

- `libnetsnmpagent.so.30` -> `libnetsnmpagent.so.35`
- `libnetsnmp.so.30` -> `libnetsnmp.so.35`

## Estrutura do Projeto

O projeto contém os seguintes arquivos principais:

- `debian/control`: Arquivo de controle do pacote `.deb`, especificando as dependências e metadados do pacote.
- `debian/postinst`: Script de pós-instalação que cria os links simbólicos necessários.

## Pré-Requisitos

Para construir e instalar o pacote `.deb`, você precisará de:

- Ferramentas de desenvolvimento de pacotes para Debian (`dpkg-deb`, `dpkg-buildpackage`).
- Permissões de superusuário para criar e remover links simbólicos no diretório de bibliotecas do sistema.

## Instruções de Construção

1. Clone este repositório:

2. Construa o pacote `.deb`:

    ```bash
    dpkg-deb --build .
    ```

3. O pacote `.deb` será gerado no diretório atual.
