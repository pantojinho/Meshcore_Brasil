> 🇧🇷 Versão em Português | [English version](README_EN.md)

# MeshCore Brasil

Cliente Flutter de código aberto para dispositivos de rede mesh LoRa MeshCore.

## Visão Geral

O MeshCore Brasil é um aplicativo móvel multiplataforma para comunicação com dispositivos de rede mesh LoRA MeshCore via Bluetooth Low Energy (BLE). O aplicativo permite comunicação de longo alcance e offline através de mensagens peer-to-peer, canais públicos e recursos de rede mesh.

**Site:** [meshcoreopen.org](https://meshcoreopen.org/)

<a href="http://apps.obtainium.imranr.dev/redirect.html?r=obtainium://add/https://github.com/pantojinho/Meshcore_Brasil">
        <img src="assets/badges/badge_obtainium.png" height="80" align="center" alt="Get it on Obtainium"/>
</a>

## Capturas de Tela

<table>
  <tr>
    <td><img src="docs/screenshots/contacts.jpg" width="200"/><br/><p align="center"><b>Contatos</b></p></td>
    <td><img src="docs/screenshots/chat1.jpg" width="200"/><br/><p align="center"><b>Chat</b></p></td>
    <td><img src="docs/screenshots/chat2.jpg" width="200"/><br/><p align="center"><b>Reações</b></p></td>
    <td><img src="docs/screenshots/map.jpg" width="200"/><br/><p align="center"><b>Mapa</b></p></td>
    <td><img src="docs/screenshots/channels.jpg" width="200"/><br/><p align="center"><b>Canais</b></p></td>
  </tr>
</table>

## Funcionalidades

### Funcionalidades Principais

- **Mensagens Diretas**: Conversas privadas e criptografadas com contatos individuais
- **Canais Públicos**: Transmissão de mensagens para assinantes de canais na rede mesh
- **Gerenciamento de Contatos**: Organize contatos, acompanhe o último acesso e gerencie o histórico de conversas
- **Grupos de Contatos**: Crie grupos personalizados para organizar seus contatos da rede mesh
- **Reações a Mensagens**: Reaja a mensagens com respostas em emoji
- **Respostas a Mensagens**: Encadeie conversas com funcionalidade de resposta integrada

### Rede Mesh

- **Visualização de Caminhos**: Visualize rotas e qualidade de sinal para cada contato
- **Gerenciamento de Rotas**: Substituição manual de caminhos e rotação automática de rotas
- **Métricas de Sinal**: Acompanhamento de SNR (Signal-to-Noise Ratio) em tempo real
- **Descoberta de Nós**: Detecção automática de nós mesh próximos
- **Suporte a Repeaters**: Conecte-se e gerencie nós repeater para alcance estendido

### Mapa e Localização

- **Visualização de Mapa ao Vivo**: Visualização em tempo real dos nós da rede mesh em um mapa interativo
- **Filtro de Nós**: Filtre por tipo de nó (chat, repeater, sensor) e intervalo de tempo
- **Compartilhamento de Localização**: Compartilhe coordenadas GPS e marcadores personalizados com contatos
- **Mapas Offline**: Baixe tiles de mapa para uso offline em áreas remotas (com [StadiaMaps](https://stadiamaps.com/pricing/) API-Key de Assinatura Gratuita)
- **Coordenadas MGRS**: Suporte para formato de coordenadas Military Grid Reference System

### Gerenciamento de Dispositivos

- **Conexão BLE, USB, TCP**: Escaneie e conecte-se a dispositivos MeshCore via Bluetooth, USB ou TCP
- **Configurações do Dispositivo**: Configure parâmetros de rádio, configurações de energia e opções de rede
- **Monitoramento de Bateria**: Status da bateria em tempo real com curvas de voltagem específicas por química
- **Atualizações de Firmware**: Atualizações de firmware over-the-air via BLE (em breve)

### Repeater Hub

- **Acesso CLI**: Interface de linha de comando completa para nós repeater
- **Gerenciamento de Configurações**: Configure comportamento do repeater, limites de energia e configurações de rede
- **Painel de Estatísticas**: Visualize o tráfego do repeater, clientes conectados e integridade do sistema
- **Gerenciamento Remoto**: Administre repeaters de qualquer lugar da rede mesh

## Detalhes Técnicos

### Arquitetura

- **Framework**: Flutter 3.38.5 / Dart 3.10.4
- **Gerenciamento de Estado**: Provider pattern com ChangeNotifier
- **Protocolo BLE**: Nordic UART Service (NUS) sobre Bluetooth Low Energy
- **Armazenamento**: Banco de dados SQLite local para mensagens e dados de contatos
- **Criptografia**: Criptografia ponta-a-ponta para mensagens privadas usando o protocolo MeshCore

### Suporte de Plataformas

| Funcionalidade     | Android (API 21+) | iOS (12+) | Linux | Windows | macOS |                Web                |
|--------------------|:-----------------:|:---------:|:-----:|:-------:|:-----:|:---------------------------------:|
| BLE companion      | ✅                | ✅        | ✅   | ✅      | ✅    | ✅                                |
| USB companion      | ✅                | 🚧        | ✅   | ✅      | ✅    | ✅                                |
| TCP companion      | ✅                | 🚧        | ✅   | ✅      | ✅    | ❌<br>(requer websocket bridge)   |
| Funcionalidades Core | ✅              | ✅        | ✅   | ✅      | ✅    | ✅                                |
| Rede Mesh          | ✅                | ✅        | ✅   | ✅      | ✅    | ✅                                |
| Mapa e Localização | ✅                | ✅        | ✅   | ✅      | ✅    | ✅                                |
| Gerenciamento de Dispositivos | ✅    | ✅        | ✅   | ✅      | ✅    | ✅                                |
| Repeater Hub       | ✅                | ✅        | ✅   | ✅      | ✅    | ✅                                |

### Dependências

| Pacote | Finalidade |
|---------|---------|
| flutter_blue_plus | Comunicação Bluetooth Low Energy |
| provider | Gerenciamento de estado |
| shared_preferences | Armazenamento local de chave-valor (escopo por dispositivo) |
| flutter_map | Exibição de mapa interativo |
| latlong2 | Manipulação de coordenadas geográficas |
| flutter_local_notifications | Suporte a notificações em segundo plano |
| pointycastle | Operações criptográficas |
| llamadart | Tradução de mensagens com LLM no dispositivo |
| intl | Internacionalização e formatação de datas |

## Primeiros Passos

### Pré-requisitos

- Flutter SDK 3.38.5 ou superior
- Android Studio / Xcode (para desenvolvimento móvel)
- Um dispositivo LoRa compatível com MeshCore

### Instalação

1. **Clone o repositório**

   ```bash
   git clone https://github.com/pantojinho/Meshcore_Brasil.git
   cd Meshcore_Brasil
   ```

2. **Instale as dependências**

   ```bash
   flutter pub get
   ```

3. **Execute o aplicativo**

   ```bash
   flutter run
   ```

### Build para Release

**Android APK:**

```bash
flutter build apk --release
```

**iOS:**

```bash
flutter build ios --release
```

## Estrutura do Projeto

```
lib/
├── main.dart                    # App entry point
├── connector/
│   ├── meshcore_connector.dart  # BLE communication & state management
│   ├── meshcore_protocol.dart   # Protocol definitions & frame parsing
│   └── meshcore_uuids.dart      # Device names and IDs (add prefixes here!)
├── screens/
│   ├── scanner_screen.dart      # Device scanning (home screen)
│   ├── contacts_screen.dart     # Contact list
│   ├── chat_screen.dart         # Direct messaging
│   ├── channels_screen.dart     # Public channels
│   ├── map_screen.dart          # Network visualization map
│   ├── settings_screen.dart     # Device settings
│   └── repeater_hub_screen.dart # Repeater management
├── models/
│   ├── contact.dart             # Contact data model
│   ├── message.dart             # Message data structure
│   └── channel.dart             # Channel definitions
├── services/
│   ├── notification_service.dart      # Push notifications
│   ├── message_retry_service.dart     # Automatic message retry
│   ├── background_service.dart        # Background BLE connection
│   └── map_tile_cache_service.dart    # Offline map storage
└── storage/
    ├── message_store.dart       # Message persistence
    ├── contact_store.dart       # Contact database
    └── unread_store.dart        # Unread message tracking
```

## Protocolo BLE

### Nordic UART Service (NUS)

- **Service UUID**: `6e400001-b5a3-f393-e0a9-e50e24dcca9e`
- **RX Characteristic**: `6e400002-b5a3-f393-e0a9-e50e24dcca9e` (Write to device)
- **TX Characteristic**: `6e400003-b5a3-f393-e0a9-e50e24dcca9e` (Notify from device)

### Descoberta de Dispositivos

Os dispositivos são descobertos escaneando anúncios BLE com prefixos de nomes de dispositivos MeshCore conhecidos. Atualmente são:
    - `MeshCore-`
    - `Whisper-`
    - `WisCore-`
    - `HT-`
    - `LowMesh_MC_`
    - `NRF52`

Novos prefixos de dispositivos podem ser adicionados em `lib/connector/meshcore_uuids.dart`.


### Formato de Mensagens

As mensagens são transmitidas como frames binários usando um protocolo customizado otimizado para transmissão LoRa. Consulte `meshcore_protocol.dart` para definições de estrutura de frames.

## Configuração

### Configurações do Aplicativo

- **Tema**: Padrão do sistema, modo claro ou escuro
- **Idioma**: Use um dos 15 idiomas (Inglês, Chinês, Francês, Espanhol, Português, Alemão, Holandês, Polonês, Sueco, Italiano, Eslovaco, Esloveno, Búlgaro, Russo, Ucraniano)
- **Notificações**: Configurável para mensagens, canais e anúncios de nós
- **Química da Bateria**: Suporte para baterias NMC, LiFePO4 e LiPo
- **Reenvio de Mensagens**: Reenvio automático com limpeza de caminho configurável

### Configurações do Dispositivo

- **Potência de Rádio**: Ajuste de potência de transmissão (10-30 dBm)
- **Frequência**: Configuração de frequência LoRa
- **Largura de Banda**: Seleção de largura de banda do canal
- **Spreading Factor**: Compromisso entre alcance e velocidade
- **Network ID**: Identificador da rede mesh

## Contribuindo

Este é um projeto de código aberto. Contribuições são bem-vindas!

### Diretrizes de Desenvolvimento

- Siga o guia de estilo do Flutter
- Use componentes do Material 3
- Escreva mensagens de commit claras
- Teste tanto em Android quanto em iOS antes de enviar PRs

### Estilo de Código

- Prefira `StatelessWidget` com `Consumer` para UI reativa
- Use construtores `const` quando possível
- Mantenha funções pequenas e focadas
- Evite abstrações prematuras
- Execute dart format em todas as alterações antes de enviar

## Suporte

Para issues, dúvidas ou solicitações de funcionalidades, abra uma issue no GitHub:
<https://github.com/pantojinho/Meshcore_Brasil/issues>

## Agradecimentos

- Construído com [Flutter](https://flutter.dev/)
- Tiles de mapa de [OpenStreetMap](https://www.openstreetmap.org/)
