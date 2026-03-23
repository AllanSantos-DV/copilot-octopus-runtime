# Copilot Octopus Runtime

[English version below](#english-version)

## 🇧🇷 Versão em Português

### O que é?

**Copilot Octopus Runtime** é o runtime do sistema Copilot Octopus — uma solução que permite controlar o VS Code remotamente através do GitHub Copilot usando um dispositivo Android.

Este repositório contém apenas os **binários de release** (daemon Windows e app Android). O código-fonte é mantido privado.

### Como funciona?

O sistema é composto por três partes:

1. **Extensão VS Code** ([Copilot Delegate](https://github.com/allansantos-dv/vscode)) - Instalada no VS Code, permite controle via Copilot
2. **Daemon Windows** (este repo) - Baixado automaticamente pela extensão, gerencia a comunicação
3. **App Android** (este repo) - Conecta-se ao daemon e interage com o Copilot

A extensão Copilot Delegate baixa automaticamente o daemon deste repositório quando necessário.

### Componentes

- **Daemon (Windows)**: Serviço que roda em background gerenciando conexões WebSocket entre o VS Code e o dispositivo Android
- **App Android (APK)**: Aplicativo móvel para enviar comandos e receber respostas do Copilot

### Requisitos

- **Rede local (WiFi)**: Por padrão, o Android e o PC devem estar na mesma rede local
- **VS Code**: Com a extensão Copilot Delegate instalada
- **Windows**: Para executar o daemon

### Acesso Remoto

Para acessar seu VS Code de qualquer lugar (fora da rede local), recomendamos:

- **[Tailscale](https://tailscale.com/)**: VPN mesh que cria uma rede privada entre seus dispositivos
  - Instale no PC Windows e no dispositivo Android
  - Conecte ambos à mesma Tailnet
  - Use o IP da Tailnet para conectar o app ao daemon

### Roadmap

Próximas melhorias planejadas:

- ☁️ **Cloudflare Tunnel**: Opção de túnel seguro sem VPN
- 🔥 **Firebase Realtime Database**: Modo relay para conexões através da nuvem
- 📱 **Versão iOS**: App para iPhone/iPad

### Downloads

Acesse a [página de releases](https://github.com/allansantos-dv/copilot-octopus-runtime/releases) para baixar:
- Daemon Windows (ZIP)
- App Android (APK)

---

## 🇬🇧 English Version

### What is it?

**Copilot Octopus Runtime** is the runtime for the Copilot Octopus system — a solution that enables remote control of VS Code through GitHub Copilot using an Android device.

This repository contains only the **release binaries** (Windows daemon and Android app). The source code is kept private.

### How does it work?

The system consists of three parts:

1. **VS Code Extension** ([Copilot Delegate](https://github.com/allansantos-dv/vscode)) - Installed in VS Code, enables Copilot control
2. **Windows Daemon** (this repo) - Automatically downloaded by the extension, manages communication
3. **Android App** (this repo) - Connects to the daemon and interacts with Copilot

The Copilot Delegate extension automatically downloads the daemon from this repository when needed.

### Components

- **Daemon (Windows)**: Background service managing WebSocket connections between VS Code and the Android device
- **Android App (APK)**: Mobile application to send commands and receive responses from Copilot

### Requirements

- **Local network (WiFi)**: By default, Android and PC must be on the same local network
- **VS Code**: With the Copilot Delegate extension installed
- **Windows**: To run the daemon

### Remote Access

To access your VS Code from anywhere (outside the local network), we recommend:

- **[Tailscale](https://tailscale.com/)**: Mesh VPN that creates a private network between your devices
  - Install on Windows PC and Android device
  - Connect both to the same Tailnet
  - Use the Tailnet IP to connect the app to the daemon

### Roadmap

Planned improvements:

- ☁️ **Cloudflare Tunnel**: Secure tunnel option without VPN
- 🔥 **Firebase Realtime Database**: Relay mode for cloud-based connections
- 📱 **iOS Version**: App for iPhone/iPad

### Downloads

Visit the [releases page](https://github.com/allansantos-dv/copilot-octopus-runtime/releases) to download:
- Windows Daemon (ZIP)
- Android App (APK)

---

## License

MIT License - See [LICENSE](LICENSE) file for details.
