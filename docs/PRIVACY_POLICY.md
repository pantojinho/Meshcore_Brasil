# Política de Privacidade do MeshCore Brasil

**Última atualização:** 16 de Julho de 2026

## Introdução

O MeshCore Brasil ("o App") é um aplicativo open-source em Flutter para comunicação com dispositivos LoRa mesh networking MeshCore. Esta Política de Privacidade explica como o App trata suas informações.

## Coleta de Dados

### Dados que NÃO Coletamos

O MeshCore Brasil **não**:
- Coleta informações pessoais
- Envia dados para servidores externos (exceto requisições de mapas)
- Rastreia seu uso ou comportamento
- Utiliza serviços de analytics
- Exige criação de conta
- Compartilha quaisquer dados com terceiros

### Dados Armazenados Localmente no Seu Dispositivo

O App armazena os seguintes dados **apenas localmente no seu dispositivo**:

- **Mensagens**: Mensagens de chat enviadas e recebidas através da rede mesh
- **Contatos**: Nomes e identificadores de contatos da rede mesh
- **Configurações do App**: Suas preferências (tema, idioma, notificações)
- **Configurações de Canais**: Configuração dos canais da rede mesh
- **Histórico de Mensagens**: Histórico de caminho (path) para roteamento de mensagens
- **Logs de Debug**: Logs opcionais de BLE e do app (se ativados pelo usuário)
- **Tiles de Mapa em Cache**: Dados de mapa offline para a funcionalidade de mapas

Todos os dados armazenados localmente permanecem no seu dispositivo e nunca são transmitidos para nós ou qualquer terceiro.

## Permissões

O App requer certas permissões do dispositivo para funcionar:

### Permissões de Bluetooth
- **BLUETOOTH, BLUETOOTH_ADMIN** (Android 11 e inferior)
- **BLUETOOTH_SCAN, BLUETOOTH_CONNECT, BLUETOOTH_ADVERTISE** (Android 12+)

Estas permissões são usadas exclusivamente para descobrir e se comunicar com dispositivos MeshCore via Bluetooth Low Energy (BLE).

### Permissão de Localização
- **ACCESS_FINE_LOCATION, ACCESS_COARSE_LOCATION**

Exigida pelo Android para escaneamento BLE no Android 11 e inferior. O App **não** rastreia ou armazena sua localização. Dados de localização podem ser opcionalmente compartilhados pela rede mesh se você ativar os recursos de compartilhamento de localização.

### Permissão de Internet
- **INTERNET**

Usada apenas para baixar tiles de mapa dos servidores OpenStreetMap ao usar o recurso de mapa. Nenhum dado pessoal é transmitido.

### Permissão de Notificações
- **POST_NOTIFICATIONS** (Android 13+)

Usada para exibir notificações de mensagens recebidas quando o app está em segundo plano.

### Permissões de Serviço em Segundo Plano
- **FOREGROUND_SERVICE, FOREGROUND_SERVICE_CONNECTED_DEVICE, WAKE_LOCK**

Usadas para manter a conexão BLE com seu dispositivo MeshCore enquanto o app está em segundo plano.

## Serviços de Terceiros

### Tiles de Mapa
O App usa servidores OpenStreetMap para exibir mapas. Ao visualizar mapas, o endereço IP do seu dispositivo pode ser visível para o servidor de tiles. Nenhum outro dado é compartilhado. Consulte a [Política de Privacidade do OpenStreetMap](https://wiki.osmfoundation.org/wiki/Privacy_Policy) para mais informações.

### Busca de GIFs (Giphy)
O App inclui um seletor de GIFs powered by Giphy. Ao usar a busca de GIFs:
- Suas consultas de busca são enviadas aos servidores da API do Giphy
- O IP do seu dispositivo é visível para o Giphy
- O Giphy pode coletar dados de uso conforme sua própria política de privacidade

A busca de GIFs é opcional e só é ativada quando você escolhe usá-la. Consulte a [Política de Privacidade do Giphy](https://support.giphy.com/hc/en-us/articles/360032872931-GIPHY-Privacy-Policy) para mais informações.

## Comunicações da Rede Mesh

Mensagens enviadas através da rede mesh MeshCore são transmitidas via radiofrequência para outros dispositivos mesh. O App em si não controla nem monitora essas comunicações além de facilitar a conexão entre seu dispositivo móvel e o hardware MeshCore.

## Segurança de Dados

Todos os dados são armazenados localmente no seu dispositivo usando mecanismos padrão do Flutter/Android. O App não implementa criptografia adicional para dados armazenados localmente além do que o sistema operacional oferece.

## Privacidade Infantil

O App não coleta knowingly nenhuma informação pessoal de crianças menores de 13 anos.

## Código Aberto

O MeshCore Brasil é software open-source. Você pode revisar o código-fonte completo para verificar estas práticas de privacidade no [repositório do projeto](https://github.com/pantojinho/Meshcore_Brasil).

## Alterações nesta Política

Podemos atualizar esta Política de Privacidade periodicamente. Quaisquer alterações serão refletidas na data de "Última atualização" no topo desta política.

## Contato

Se você tem dúvidas sobre esta Política de Privacidade ou as práticas de privacidade do App, por favor abra uma issue no [repositório GitHub do projeto](https://github.com/pantojinho/Meshcore_Brasil/issues).

---

**Resumo**: O MeshCore Brasil é um app que respeita sua privacidade e armazena todos os dados localmente no seu dispositivo. Não coletamos, rastreamos ou compartilhamos suas informações pessoais.
