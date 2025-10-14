<!-- Links de apoio: https://simpleicons.org/?q=status -->
<!-- Link de apoio: https://github.com/VishwaGauravIn/pretty-readme-badges -->

<div align="center"> 
  <img src="https://avatars.githubusercontent.com/u/128941?v=4" width="150" height="150"> <!-- logo Zulip -->

  <h1>Zulip Flutter</h1> <!-- Título -->
   
 [![GitHub tag](https://img.shields.io/github/tag/ufmt-ic/zulip-flutter?include_prereleases=&sort=semver&color=blue)](https://github.com/ufmt-ic/zulip-flutter/tags)
 [![Status - active](https://img.shields.io/static/v1?label=Status&message=active&color=73baa0&logo=flutter&logoColor=white)](https://)
 <img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/ufmt-ic/zulip-flutter" />

</div>

## 🧾 Descrição do Projeto

Aplicativo **Zulip Flutter** — cliente mobile multiplataforma do sistema de mensagens **Zulip**, desenvolvido com **Flutter** e compatível com Android, iOS, Linux, macOS e Windows.  
Este repositório contém o código-fonte e pipelines de integração contínua (CI) utilizados para compilar, testar e gerar builds automatizados do aplicativo.

## 🎯 Visão do Produto

**Para** instituições e equipes que necessitam de comunicação assíncrona, organizada por tópicos e de alta segurança,  
**o** Zulip Flutter  
**é um** aplicativo mobile de mensagens baseado em streams e tópicos,  
**que** oferece experiência fluida e moderna, sincronizada com o servidor Zulip,  
**diferente de** outros mensageiros que agrupam conversas de forma linear, dificultando o acompanhamento de múltiplos temas simultaneamente.

## 🗺️ Sumário
- [📘 Descrição do Projeto](#-descrição-do-projeto)
- [🎯 Visão do Produto](#-visão-do-produto)
- [🗂️ Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [🛠️ Pré-requisitos](#-pré-requisitos)
- [📁 Estrutura de Pastas](#-estrutura-de-pastas)
- [🛰️ Utilizado por](#-utilizado-por)
- [👨‍🚀 Contribuidores](#-contribuidores)
- [🔗 Referências](#-referências)

## 🗂️ Tecnologias Utilizadas

- **Flutter 3.x** – Framework multiplataforma para criação de aplicativos móveis, desktop e web.
- **Dart** – Linguagem de programação oficial do Flutter.
- **Zulip API** – Interface REST usada para autenticação e sincronização de mensagens, streams e usuários.
- **GitHub Actions (CI/CD)** – Workflows automatizados para build, lint, testes e atualização de traduções (`.github/workflows`).
- **Android SDK / iOS SDK** – Ferramentas nativas para empacotamento e publicação.
- **intl_translation** – Suporte multilíngue via `update-translations.yml`.
- **VSCode / Android Studio** – Ambientes recomendados de desenvolvimento.
- **YAML Linter** – Verificação de formatação e boas práticas em arquivos `.yaml`.

## 🛠️ Pré-requisitos

- **Flutter SDK 3.x** ou superior  
- **Dart SDK 3.x**  
- **Android Studio** ou **VS Code** com extensão Flutter  
- **Git**  
- **Acesso ao servidor Zulip** (instância local ou hospedada)

Para configurar o ambiente:

```bash
# Clonar o repositório
git clone https://github.com/ufmt-ic/zulip-flutter.git

# Entrar na pasta
cd zulip-flutter

# Instalar dependências
flutter pub get

# Rodar no emulador ou dispositivo conectado
flutter run

zulip-flutter/
├── .github/                          # Workflows de CI/CD
│   └── workflows/
│       ├── ci.yml                    # Executa build e testes automatizados
│       └── update-translations.yml   # Atualiza arquivos de tradução
├── android/                          # Código e configurações nativas Android
├── ios/                              # Código e configurações nativas iOS
├── linux/                            # Suporte a builds Linux
├── macos/                            # Suporte a builds macOS
├── windows/                          # Suporte a builds Windows
├── lib/                              # Código-fonte principal do app
│   ├── models/                       # Modelos de dados (usuário, mensagem, stream, etc.)
│   ├── screens/                      # Telas principais do app (login, streams, mensagens)
│   ├── widgets/                      # Componentes reutilizáveis
│   ├── services/                     # Lógica de comunicação com a API Zulip
│   ├── utils/                        # Funções auxiliares e helpers
│   └── main.dart                     # Ponto de entrada do aplicativo
├── assets/                           # Ícones, fontes e imagens
├── test/                             # Testes automatizados (unitários e widget tests)
├── tools/                            # Scripts e utilitários
├── docs/                             # Documentação do projeto
├── pubspec.yaml                      # Dependências e metadados do projeto Flutter
├── analysis.options.yaml             # Regras de linting e análise de código
├── l10n.yaml                         # Configuração de localização e idiomas
├── build.yaml                        # Configurações de build
└── README.md                         # Documento atual
