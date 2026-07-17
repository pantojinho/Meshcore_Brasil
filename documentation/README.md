# MeshCore Brasil — Documentação de Funcionalidades

O MeshCore Brasil é um cliente Flutter de código aberto para dispositivos de rede mesh LoRa MeshCore. Esta documentação abrange todas as funcionalidades voltadas ao usuário, como acessá-las e o que cada uma faz.

## Sumário

1. [Scanner & Conexão](scanner-and-connection.md) - Escaneamento BLE, USB serial e conexão TCP
2. [Navegação](navigation.md) - Fluxo do app, tela do dispositivo e navegação rápida
3. [Contatos](contacts.md) - Gerenciamento de contatos, grupos, descoberta e compartilhamento
4. [Chat & Mensagens](chat-and-messaging.md) - Mensagens diretas, status de mensagens, reações e reenvios
5. [Canais](channels.md) - Canais de transmissão, comunidades e chat de canal
6. [Mapa & Localização](map-and-location.md) - Mapa de nós, rastreamento de caminho, linha de visada e cache offline
7. [Configurações](settings.md) - Configurações do dispositivo, do app, rádio e exportações
8. [Notificações](notifications.md) - Notificações do sistema, indicadores de não lidas e preferências de notificação
9. [Gerenciamento de Repetidores](repeater-management.md) - Hub de repetidores, status, CLI, telemetria e vizinhos
10. [Funcionalidades Adicionais](additional-features.md) - Seletor de GIF, localização, logs de depuração, compressão SMAZ e mais
11. [Caminhos de Roteamento](routing-paths.md) - Codificação de caminho, validação, detecção de capacidade do dispositivo e armazenamento
12. [Protocolo BLE & Camada de Dados](ble-protocol.md) - Referência técnica do protocolo de comunicação e arquitetura de dados

## Visão Geral do App

O MeshCore Brasil se conecta a rádios mesh LoRa MeshCore via BLE, USB ou TCP. Uma vez conectado, os usuários podem:

- **Conversar** com outros nós da mesh via mensagens diretas criptografadas
- **Transmitir** em canais compartilhados (público, hashtag, privado ou escopo de comunidade)
- **Visualizar nós no mapa** com localizações GPS, posições previstas e rastros de caminho
- **Gerenciar repetidores** com acesso CLI, telemetria, informações de vizinhos e configurações
- **Compartilhar contatos** via URIs `meshcore://` e QR codes
- **Configurar parâmetros de rádio** incluindo frequência, potência, largura de banda e spreading factor
- **Armazenar mapas offline** para uso sem conexão à internet
- **Analisar linha de visada** entre nós com perfis de elevação do terreno
