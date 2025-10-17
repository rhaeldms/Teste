<!-- Links de apoio: https://simpleicons.org/?q=status -->
<!-- Link de apoio: https://github.com/VishwaGauravIn/pretty-readme-badges -->

<div align="center"> 
  <img src="https://avatars.githubusercontent.com/u/128941?v=4" width="150" height="150"> <!-- logo Zulip -->

  <h1>Zulip Flutter</h1> <!-- Título -->
   
  <a href="https://github.com/ufmt-ic/zulip-flutter/tags">
    <img alt="GitHub tag" src="https://img.shields.io/github/tag/ufmt-ic/zulip-flutter?include_prereleases=&sort=semver&color=blue" />
  </a>
  <a href="#">
    <img alt="Status - active" src="https://img.shields.io/static/v1?label=Status&message=active&color=73baa0&logo=flutter&logoColor=white" />
  </a>
  <img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/ufmt-ic/zulip-flutter" />
</div>

---

## 🧾 Descrição do Projeto

O **Zulip Flutter** é o aplicativo oficial do Zulip para **Android e iOS**, desenvolvido com **Flutter**.

Este aplicativo [foi lançado][] como o principal aplicativo móvel do Zulip em **junho de 2025**.  
Ele substituiu o [aplicativo móvel anterior do Zulip][] desenvolvido com **React Native**.

O aplicativo combina a poderosa arquitetura de tópicos do Zulip com uma interface moderna, multiplataforma e de alto desempenho.

[foi lançado]: https://blog.zulip.com/flutter-mobile-app-launch  
[aplicativo móvel anterior do Zulip]: https://github.com/zulip/zulip-mobile#readme

---

## 🎯 Visão do Produto

**Para** instituições e equipes que necessitam de comunicação assíncrona, organizada e segura,  
**o** Zulip Flutter  
**é um** aplicativo mobile de mensagens baseado em *streams* e *topics*,  
**que** oferece uma experiência fluida, com notificações integradas e sincronização contínua,  
**ao contrário de** mensageiros lineares, que misturam conversas e dificultam o acompanhamento de múltiplos assuntos.

---

## 📱 Obtenha o aplicativo

As versões de lançamento do aplicativo estão disponíveis aqui:

- 📲 **[Zulip para iOS](https://apps.apple.com/app/zulip/id1203036395)** na App Store da Apple  
- 🤖 **[Zulip para Android](https://play.google.com/store/apps/details?id=com.zulipmobile)** na Google Play Store  
  - Ou, se você não usa a Google Play, você pode **[baixar um APK](https://github.com/zulip/zulip-flutter/releases/latest)** da compilação oficial que publicamos no GitHub.

---

## 🗺️ Sumário
- [🧾 Descrição do Projeto](#-descrição-do-projeto)
- [🎯 Visão do Produto](#-visão-do-produto)
- [📱 Obtenha o aplicativo](#-obtenha-o-aplicativo)
- [🗂️ Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [🛠️ Pré-requisitos e Configuração](#-pré-requisitos-e-configuração)
- [📁 Estrutura de Pastas](#-estrutura-de-pastas)
- [🤝 Contribuindo](#-contribuindo)
  - [Escolhendo uma issue para trabalhar](#escolhendo-uma-issue-para-trabalhar)
  - [Fazendo perguntas e obtendo ajuda](#fazendo-perguntas-e-obtendo-ajuda)
  - [Enviando um pull request](#enviando-um-pull-request)
- [🧪 Testes](#-testes)
- [📝 Notas](#-notas)
  - [Design de UI](#design-de-ui)
  - [Escrevendo testes](#escrevendo-testes)
  - [`check` vs. `expect`](#check-vs-expect)
  - [Editando tipos de API](#editando-tipos-de-api)
  - [Suporte para desktop](#suporte-para-desktop)
- [📜 Licença](#-licença)
- [👨‍🚀 Contribuidores](#-contribuidores)
- [🔗 Referências](#-referências)

---

## 🗂️ Tecnologias Utilizadas

- **Flutter 3.x** – Framework multiplataforma para Android, iOS, desktop e web.  
- **Dart SDK 3.x** – Linguagem principal do Flutter.  
- **Zulip REST API** – Comunicação com o servidor Zulip.  
- **GitHub Actions (CI/CD)** – Workflows automatizados (`.github/workflows/ci.yml` e `update-translations.yml`).  
- **SQLite** – Dependência usada em partes da suíte de testes.  
- **package:checks** – Framework moderno para asserções em testes Dart.  
- **Figma** – Base dos layouts oficiais de UI.  
- **VSCode / Android Studio** – Ambientes de desenvolvimento recomendados.

---

## 🛠️ Pré-requisitos e Configuração

Executar o aplicativo requer apenas uma configuração padrão do Flutter, usando o canal `main`:

1. Siga o **[guia de instalação do Flutter](https://docs.flutter.dev/get-started/install)** para a plataforma de sua escolha.  
2. Mude para a versão mais recente do Flutter executando:
   ```bash
   flutter channel main
   flutter upgrade
   flutter doctor
3. Inicie o aplicativo:
   flutter run
4. Dependência adicional para testes: instale o SQLite (ex.: sudo apt install libsqlite3-dev).
5. Windows (passo adicional): git config core.autocrlf input (veja docs/setup.md#autocrlf).

Para mais detalhes e configurações incomuns, veja docs/setup.md.
Se encontrar problemas, consulte docs/setup.md#troubleshooting e, se necessário, veja como pedir ajuda.

Versão do Flutter

Usamos a versão mais recente do Flutter (branch main).
Isso implica usar também o Dart SDK mais recente. Acompanhamos o upstream para receber correções e recursos rapidamente.
Não fixamos versão específica (o Flutter não oferece mecanismo nativo para isso); quando necessário, avaliaremos soluções. Consulte a issue #15.

📁 Estrutura de Pastas
   ```bash
zulip-flutter/
├── .github/workflows/
│   ├── ci.yml                    # Build e testes automatizados
│   └── update-translations.yml   # Atualização automática de traduções
├── android/                      # Projeto Android nativo
├── ios/                          # Projeto iOS nativo
├── linux/ | macos/ | windows/    # Builds desktop (para desenvolvimento)
├── lib/                          # Código principal do app Flutter
│   ├── models/                   # Modelos de dados
│   ├── screens/                  # Telas e navegação
│   ├── widgets/                  # Componentes reutilizáveis
│   ├── services/                 # Comunicação com API
│   ├── utils/                    # Funções auxiliares
│   └── main.dart                 # Ponto de entrada
├── test/                         # Testes unitários e de widgets
├── tools/                        # Scripts (ex.: tools/check)
├── assets/                       # Ícones e fontes
├── pubspec.yaml                  # Dependências Flutter
└── analysis.options.yaml         # Regras de lint
```

🤝 Contribuindo

Contribuições para este aplicativo são bem-vindas.

Se você deseja participar do Google Summer of Code com o Zulip, este foi um dos projetos para os quais aceitamos inscrições do GSoC
 em 2024 e 2025.

Escolhendo uma issue para trabalhar

Primeiro, veja o guia do projeto Zulip sobre sua primeira contribuição ao código-fonte
.
Siga as instruções para entrar no servidor da comunidade Zulip, ler sobre o que faz um ótimo colaborador do Zulip
, navegar pelos commits recentes e pelo código-fonte, e o guia do Zulip sobre Git.

Para encontrar possíveis issues em que trabalhar, veja nosso quadro do projeto
.
Procure por issues no marco mais inicial e que ainda não estejam atribuídas.

Siga o guia do Zulip sobre escolher uma issue para trabalhar
, tentando várias issues até encontrar uma na qual você esteja confiante de que conseguirá trabalhar de forma eficaz.

Depois de fazer isso, reivindique a issue publicando um comentário no tópico, dizendo que gostaria de trabalhar nela e descrevendo seu progresso.

Fazendo perguntas e obtendo ajuda

Para pedir ajuda ao trabalhar neste código-fonte, use o canal #mobile-dev-help
 em chat.zulip.org.
Antes de participar lá pela primeira vez, reserve um minuto para ler nossas normas da comunidade
.

Para conselhos mais aprofundados, veja o guia do Zulip para fazer ótimas perguntas
 e os recursos vinculados.

Enviando um pull request

Siga o guia de primeira contribuição para trabalhar em uma issue
 e enviar um pull request
.
É importante dedicar tempo para tornar seu trabalho o mais fácil possível de ser revisado.

Antes da revisão detalhada do PR, suas alterações precisam de testes (veja Escrevendo testes
) e todos os testes (novos e existentes) devem passar (veja Testes
).

Organize as mudanças em commits claros e coerentes
, seguindo o guia de estilo do Zulip.
(Dica: use o "segredo" de Greg para git log -p
 e/ou um cliente Git para ver exemplos de commits mescláveis.)

 🧪 Testes

```bash
Execute todas as formas de testes com:
tools/check
```

Veja tools/check --help para mais informações.

As duas principais suítes de teste são:

Analisador do Dart (tipagem e lint):
```bash
flutter analyze
```

Testes de unidade e widgets (em test/):
```bash
flutter test
```

Ambos os comandos aceitam caminhos e opções para filtrar execução; por exemplo, para rodar somente test/foo/bar_test.dart e casos contendo baz.

Ao editar em uma IDE, o feedback do flutter analyze é exibido diretamente; em arquivos de teste, é possível executar casos individuais.
Consulte a documentação do Flutter sobre testes unitários
.

📝 Notas
Design de UI

Para issues que exigem nova UI, normalmente há um design no Figma (linkado na issue).
O PR deve corresponder exatamente ao design, salvo justificativa clara documentada na descrição do PR.

Para cores, espaçamentos, tipografia e demais detalhes, use as definições existentes (ex.: DesignVariables, ContentTheme).
Se precisar de uma variável que ainda não exista, adicione-a seguindo o padrão do projeto.
Antes de enviar, revise seu próprio trabalho comparando com o Figma.

Escrevendo testes

Escrevemos testes para todas as alterações no código Dart (inclusive UI e chamadas de rede/APIs externas).

UI: testWidgets + utilitários (TestZulipBinding, TestGlobalStore, testBinding.globalStore).

API Zulip: FakeApiConnection.

Rede genérica: FakeHttpClient + withHttpClient (package:http).

Plugins/APIs externas: encapsular via ZulipBinding (adicione membros quando necessário).

Caso encontre código legado sem testes (protótipos antigos), ao modificar, escreva testes para a mudança e, se possível, para a lógica pré-existente.

check vs. expect

Preferimos o package:checks
 (prévia da equipe Dart), que deve substituir o antigo matcher.
Ao encontrar exemplos com expect, traduza-os para check.
Veja guia de migração
 e API
.
Feedbacks podem ser abertos no rastreador de testes do Dart
.

Editando tipos de API
Compatibilidade com o servidor

Suportamos Zulip Server 7.0+.

Para recursos mais novos, use comentários TODO(server-N) (padrão existente no código).

Exigir todos os parâmetros nos construtores de API

Evite valores padrão, inclusive null.

Prefira required this.foo (mesmo se foo for anulável), pois ausência/nulo tem semântica na API do Zulip.

Em testes, se for incômodo passar tudo manualmente, use fábricas em test/example_data.dart.

Arquivos gerados

Ao editar definições de tipo, regerar o código associado (serialização JSON).

Execute, por exemplo:
```bash
flutter pub run build_runner build
```

Suporte para desktop

O app é destinado a Android e iOS. Em desktop, o suporte é apenas para desenvolvimento:

Layout/UX otimizados para mobile (não adaptamos para paradigmas desktop).

Integrações externas (links, câmera, etc.) implementadas somente em Android/iOS.

O app é executável e a funcionalidade principal funciona em Linux e macOS; não há colaboradores regulares usando Windows, mas aceitamos correções.

Motivação: para desenvolvimento, rodar em desktop ajuda a testar responsividade (ex.: redimensionar janela livremente).

📜 Licença

Copyright © 2022 Kandra Labs, Inc.

Licenciado sob a Licença Apache, Versão 2.0.
Você pode obter uma cópia em:

```bash
http://www.apache.org/licenses/LICENSE-2.0
```

Salvo exigido por lei ou acordado por escrito, o software é distribuído “NO ESTADO EM QUE SE ENCONTRA”, SEM GARANTIAS de qualquer tipo.
Consulte a Licença para permissões e limitações específicas.
Inclui trabalhos de terceiros sob licenças livres e de código aberto, redistribuídos conforme seus termos.
