# Guia de Deploy TestFlight e App Store

## Pré-requisitos

- [x] Conta Apple Developer ($99/ano) - [developer.apple.com](https://developer.apple.com)
- [x] Xcode instalado
- [x] App Apple Transporter instalado
- [x] Ícones do app prontos (1024x1024px)
- [x] Bundle ID configurado: `com.monitormx.meshcoreopen`

## Passo 1: Registrar o Bundle Identifier

1. Acesse [Apple Developer - Identifiers](https://developer.apple.com/account/resources/identifiers/list)
2. Clique no botão **"+"**
3. Selecione **"App IDs"** → Continue
4. Selecione **"App"** → Continue
5. Preencha:
   - **Description**: Meshcore Open
   - **Bundle ID**: Explicit - `com.monitormx.meshcoreopen`
   - **Capabilities**: Deixe os padrões (ou adicione conforme necessário)
6. Clique em **Continue** → **Register**

## Passo 2: Criar o App no App Store Connect

1. Acesse o [App Store Connect](https://appstoreconnect.apple.com)
2. Faça login com seu Apple ID
3. Clique em **"My Apps"**
4. Clique no botão **"+"** → **"New App"**
5. Preencha o formulário:
   - **Platforms**: iOS
   - **Name**: Meshcore Open
   - **Primary Language**: English (U.S.)
   - **Bundle ID**: Selecione `com.monitormx.meshcoreopen` no menu suspenso
   - **SKU**: `meshcore-open-001` (ou qualquer identificador único)
   - **User Access**: Full Access
6. Clique em **"Create"**

## Passo 3: Compilar o IPA

Execute estes comandos a partir do diretório do projeto:

```bash
# Adicionar CocoaPods ao PATH
export PATH="/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"

# Limpar compilações anteriores
../flutter/bin/flutter clean

# Compilar IPA para App Store
../flutter/bin/flutter build ipa
```

O IPA será criado em: `build/ios/ipa/meshcore_open.ipa`

## Passo 4: Enviar para o App Store Connect via Transporter

1. **Abra o Apple Transporter**
   - Inicie a partir da pasta Applications
   - Faça login com seu Apple ID

2. **Enviar o IPA**
   - Arraste e solte `build/ios/ipa/meshcore_open.ipa` no Transporter
   - Clique em **"Deliver"**
   - Aguarde a conclusão do upload (geralmente 1-5 minutos)

3. **Processamento**
   - A Apple processará seu build (10-30 minutos)
   - Você receberá um e-mail quando o processamento for concluído

## Passo 5: Configurar Metadados no App Store Connect

### Informações do App
1. No App Store Connect, acesse seu app
2. Preencha as informações necessárias:
   - **Subtitle**: Descrição curta (máximo 30 caracteres)
   - **Privacy Policy URL**: Obrigatório para apps com Bluetooth
   - **Category**: Utilities ou Productivity
   - **Age Rating**: Complete o questionário

### Listagem na App Store
1. Acesse a aba **App Store**
2. Envie as **Screenshots** (obrigatório):
   - iPhone 6.7" display (1290 x 2796 pixels) - Pelo menos 1 screenshot
   - iPhone 6.5" display (1242 x 2688 pixels) - Pelo menos 1 screenshot
   - Opcional: Screenshots para iPad

3. Preencha a **Description**:
   ```
   Meshcore Open is a Flutter client for MeshCore LoRa mesh networking devices.

   Features:
   - BLE connectivity to MeshCore devices
   - Real-time mesh network communication
   - Map visualization with OpenStreetMap
   - Community management with QR code scanning
   - Message tracking and retry system

   Connect to your MeshCore LoRa device and start communicating over the mesh network.
   ```

4. **Keywords**: `lora,mesh,networking,bluetooth,communication`
5. **Support URL**: Sua URL do GitHub ou site
6. **Marketing URL**: (Opcional)

### Informações de Versão
1. **What's New in This Version**:
   ```
   Initial release of Meshcore Open

   - BLE device connectivity
   - Mesh network messaging
   - Map integration
   - Community features
   ```

2. **Build**: Selecione o build enviado após a conclusão do processamento

## Passo 6: Configuração do TestFlight

### Teste Interno (Sem Revisão Necessária)
1. Acesse a aba **TestFlight** no App Store Connect
2. Clique em **Internal Testing** → **"+"** para criar um grupo
3. Nomeie seu grupo (ex.: "Internal Testers")
4. Adicione a si mesmo como testador usando seu e-mail
5. Selecione o build que você enviou
6. Os testadores receberão um e-mail com o convite do TestFlight

### Teste Externo (Requer Beta Review)
1. Clique em **External Testing** → **"+"** para criar um grupo
2. Adicione o build e os testadores
3. Preencha as **Test Information**:
   - **What to Test**: Breve descrição das funcionalidades
   - **Feedback Email**: Seu endereço de e-mail
4. Clique em **Submit for Review**
5. A beta review geralmente leva de 24 a 48 horas

## Passo 7: Envio para a App Store

Quando estiver pronto para o lançamento público:

1. Acesse a aba **App Store**
2. Complete todos os metadados necessários (se ainda não fez)
3. Selecione seu build
4. Preencha as **App Review Information**:
   - **Contact Information**: Seu nome, telefone e e-mail
   - **Demo Account**: Se o app exigir login
   - **Notes**: Quaisquer instruções especiais para os revisores
5. Responda às perguntas de **Export Compliance**:
   - Seu app usa criptografia? **Yes** (usa TLS/HTTPS)
   - É necessário registro de criptografia? **No** (criptografia padrão)
6. Clique em **Add for Review**
7. Revise o resumo e clique em **Submit to App Review**

## Passo 8: Após o Envio

- **App Review**: Geralmente de 24 a 48 horas
- **Motivos Comuns de Rejeição**:
  - Política de privacidade ausente
  - Informações do app incompletas
  - Travamentos ou bugs
  - Descrição do app enganosa

- **Se Aprovado**: Você pode lançar imediatamente ou agendar uma data de lançamento
- **Se Rejeitado**: Corrija os problemas e reenvie

## Atualizando o App

Quando precisar lançar uma atualização:

1. **Atualize a versão** no `pubspec.yaml`:
   ```yaml
   version: 0.5.0+6  # Incremente a versão (0.5.0) e o número do build (+6)
   ```

2. **Compile o novo IPA**:
   ```bash
   export PATH="/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
   ../flutter/bin/flutter clean
   ../flutter/bin/flutter build ipa
   ```

3. **Envie via Transporter** (mesmo processo acima)

4. **Crie uma nova versão** no App Store Connect:
   - Clique em **"+"** ao lado de versions
   - Selecione o número da versão
   - Atualize o texto "What's New"
   - Selecione o novo build
   - Envie para revisão

## Build para macOS (Bônus)

Para compilar para macOS:

```bash
export PATH="/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
../flutter/bin/flutter build macos --release
cd build/macos/Build/Products/Release
zip -r meshcore_open-macos.zip meshcore_open.app
```

Distribuição:
- Compartilhe o arquivo zip diretamente
- Os usuários descompactam e arrastam para a pasta Applications
- Primeira execução: Clique com o botão direito → Open (para contornar o Gatekeeper)

## Solução de Problemas

### Erros de Compilação
- **CocoaPods não encontrado**: Verifique se o PATH inclui `/opt/homebrew/lib/ruby/gems/4.0.0/bin`
- **Nenhum certificado de assinatura**: Configure a Team no Xcode (Signing & Capabilities)
- **Incompatibilidade de Bundle ID**: Verifique `ios/Runner.xcodeproj/project.pbxproj`

### Erros de Upload
- **Nenhum profile encontrado**: Crie o app no App Store Connect primeiro
- **Bundle ID não registrado**: Registre no portal Apple Developer
- **Falha de autenticação**: Use o app Transporter em vez da CLI

### Problemas com TestFlight
- **Build não aparece**: Aguarde 10-30 minutos para processamento
- **Não é possível adicionar testadores**: Verifique se há vagas disponíveis (100 internos, 10.000 externos)
- **TestFlight trava**: Verifique os logs do dispositivo em Xcode → Devices & Simulators

## Arquivos Importantes

- **IPA do iOS**: `build/ios/ipa/meshcore_open.ipa`
- **App do macOS**: `build/macos/Build/Products/Release/meshcore_open.app`
- **Configuração do Bundle ID**: `ios/Runner.xcodeproj/project.pbxproj`
- **Informações de Versão**: `pubspec.yaml`

## Links Úteis

- [App Store Connect](https://appstoreconnect.apple.com)
- [Apple Developer Portal](https://developer.apple.com/account)
- [Documentação do TestFlight](https://developer.apple.com/testflight/)
- [Diretrizes de Revisão da App Store](https://developer.apple.com/app-store/review/guidelines/)
- [Deploy iOS com Flutter](https://docs.flutter.dev/deployment/ios)

## Suporte

Para problemas com:
- **Processo da App Store**: [Suporte Apple Developer](https://developer.apple.com/contact/)
- **Problemas de Build do Flutter**: [Flutter GitHub](https://github.com/flutter/flutter/issues)
- **App Meshcore Open**: [GitHub Issues](https://github.com/pantojinho/Meshcore_Brasil/issues)
