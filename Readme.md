# Zulip Flutter

O aplicativo oficial do Zulip para Android e iOS, desenvolvido com Flutter.

Este aplicativo [foi lançado][] como o principal aplicativo móvel do Zulip
em junho de 2025.
Ele substituiu o [aplicativo móvel anterior do Zulip][] desenvolvido com React Native.

[foi lançado]: https://blog.zulip.com/flutter-mobile-app-launch
[aplicativo móvel anterior do Zulip]: https://github.com/zulip/zulip-mobile#readme


## Obtenha o aplicativo

As versões de lançamento do aplicativo estão disponíveis aqui:
* [Zulip para iOS](https://apps.apple.com/app/zulip/id1203036395)
  na App Store da Apple
* [Zulip para Android](https://play.google.com/store/apps/details?id=com.zulipmobile)
  na Google Play Store
  * Ou, se você não usa a Google Play, você pode
    [baixar um APK](https://github.com/zulip/zulip-flutter/releases/latest)
    da compilação oficial que publicamos no GitHub.


## Contribuindo

Contribuições para este aplicativo são bem-vindas.

Se você deseja participar do Google Summer of Code com o Zulip,
este foi um dos projetos para os quais aceitamos [inscrições do GSoC][gsoc]
em 2024 e 2025.

[gsoc]: https://zulip.readthedocs.io/en/latest/outreach/gsoc.html#mobile-app


### Escolhendo uma issue para trabalhar

Primeiro, veja o guia do projeto Zulip sobre [sua primeira contribuição ao código-fonte][].
Siga as instruções lá para entrar no servidor da comunidade Zulip,
ler sobre [o que faz um ótimo colaborador do Zulip][],
navegar pelos commits recentes e pelo código-fonte,
e o guia do Zulip sobre Git.

Para encontrar possíveis issues em que trabalhar, veja nosso [quadro do projeto][].
Procure por issues no marco mais inicial,
e que ainda não estejam atribuídas.

Siga o guia do Zulip sobre [escolher uma issue para trabalhar][],
tentando várias issues até encontrar uma na qual você esteja confiante
de que conseguirá trabalhar de forma eficaz.

*Depois de fazer isso*, reivindique a issue publicando um comentário
no tópico da issue, dizendo que gostaria de trabalhar nela
e descrevendo seu progresso.

[sua primeira contribuição ao código-fonte]: https://zulip.readthedocs.io/en/latest/contributing/contributing.html#your-first-codebase-contribution
[o que faz um ótimo colaborador do Zulip]: https://zulip.readthedocs.io/en/latest/contributing/contributing.html#what-makes-a-great-zulip-contributor
[quadro do projeto]: https://github.com/orgs/zulip/projects/5/views/4
[escolher uma issue para trabalhar]: https://zulip.readthedocs.io/en/latest/contributing/contributing.html#picking-an-issue-to-work-on


<div id="getting-help" />

### Fazendo perguntas e obtendo ajuda

Para pedir ajuda ao trabalhar neste código-fonte, use o canal
[`#mobile-dev-help`][mobile-dev-help] em chat.zulip.org.
Antes de participar lá pela primeira vez,
certifique-se de reservar um minuto para ler nossas
[normas da comunidade][norms-getting-help].

Para conselhos mais aprofundados sobre como ir além do mínimo
representado por nossas normas da comunidade, veja
o [guia do Zulip para fazer ótimas perguntas][guide to asking great questions]
e os recursos vinculados a partir dele.

[mobile-dev-help]: https://chat.zulip.org/#narrow/stream/516-mobile-dev-help
[norms-getting-help]: https://zulip.com/development-community/#getting-help
[guia do Zulip para fazer ótimas perguntas]: https://zulip.readthedocs.io/en/latest/contributing/asking-great-questions.html


### Enviando um pull request

Siga o guia do projeto Zulip sobre sua primeira contribuição ao código-fonte
para [trabalhar em uma issue][] e [enviar um pull request][].
É importante dedicar tempo para tornar seu trabalho
o mais fácil possível de ser revisado por outras pessoas.

Dois pontos específicos a destacar:

 * Antes que possamos revisar seu PR em detalhes, suas alterações precisarão
   de testes. Veja ["Escrevendo testes"](#writing-tests) abaixo.

   Também será necessário que todos os testes novos e existentes estejam passando.
   Veja ["Testes"](#tests) abaixo sobre como executar os testes.

 * Suas alterações precisarão estar organizadas em
   [commits claros e coerentes][commit-style],
   seguindo o [guia de estilo de commits do Zulip][commit-style].
   (Use o ["segredo" de Greg para usar `git log -p`][git-log-p-secret]
   e/ou um cliente Git gráfico para ver exemplos de commits mescláveis.)

   Isso é sempre necessário antes que possamos mesclar seu PR. Dependendo da
   complexidade das suas alterações, isso também pode ser necessário antes que possamos
   revisá-lo em detalhes. (A principal exceção é quando a alteração
   deve ser um único commit — nesse caso, podemos revisá-la mesmo que a
   estrutura de commits esteja mais bagunçada.)

[trabalhar em uma issue]: https://zulip.readthedocs.io/en/latest/contributing/contributing.html#working-on-an-issue
[enviar um pull request]: https://zulip.readthedocs.io/en/latest/contributing/review-process.html
[commit-style]: https://zulip.readthedocs.io/en/latest/contributing/commit-discipline.html
[git-log-p-secret]: https://github.com/zulip/zulip-mobile/blob/main/docs/howto/git.md#git-log-secret


## Iniciando o desenvolvimento

### Configuração

Executar o aplicativo requer apenas uma configuração padrão do Flutter,
usando o canal `main` do Flutter:

1. Siga o [guia de instalação do Flutter](https://docs.flutter.dev/get-started/install)
   para a plataforma de sua escolha.
2. Mude para a versão mais recente do Flutter executando `flutter channel main`
   e `flutter upgrade` (veja [Versão do Flutter](#flutter-version) abaixo).
3. Certifique-se de que o Flutter está configurado corretamente executando `flutter doctor`.
4. Inicie o aplicativo com `flutter run` ou a partir da sua IDE.

Partes da nossa suíte de testes exigem uma dependência adicional:

5. Instale o SQLite, por exemplo, executando `sudo apt install libsqlite3-dev`.

Desenvolver no Windows requer
um [passo adicional](docs/setup.md#autocrlf):

6. Execute `git config core.autocrlf input`.

Para mais detalhes e ajuda com configurações incomuns,
veja nosso [guia completo de configuração](docs/setup.md).

Se você estiver tendo problemas ou vendo erros, consulte nossa
[seção de solução de problemas](docs/setup.md#troubleshooting).
Se isso não resolver o problema, veja a seção acima sobre
[como pedir ajuda](#getting-help).


### Versão do Flutter

Usamos a versão mais recente do Flutter a partir do branch principal (main) do Flutter.
Use `flutter channel main` e `flutter upgrade`.

Como cada versão do Flutter fornece sua própria versão do
Dart SDK, isso também significa que usamos a versão mais recente do Dart SDK.

Usar as versões mais recentes é o mesmo que o Google faz com
seus próprios aplicativos Flutter. Isso é valioso para nós porque significa que,
quando há algo que queremos corrigir no Flutter
ou um recurso que queremos adicionar,
podemos enviar um PR para o repositório principal e usá-lo assim que for incorporado.

Nós não fixamos uma versão específica do Flutter,
porque o próprio Flutter não oferece uma maneira de fazer isso.
Até agora, isso não tem sido um problema. Quando se tornar um,
vamos resolver; existem várias ferramentas para isso na comunidade Flutter.
Veja [issue #15][].

[issue #15]: https://github.com/zulip/zulip-flutter/issues/15


### Testes

Você pode executar todas as nossas formas de testes com o script `tools/check`:


Veja `tools/check --help` para mais informações.

As duas principais suítes de teste são o analisador do Dart, que realiza
verificação de tipos e lint; e nossos testes de unidade, localizados no diretório `test/`.

Você pode executar essas suítes diretamente com os comandos `flutter analyze`
e `flutter test`, respectivamente. Ambos os comandos aceitam uma lista de caminhos
de arquivos ou diretórios nos quais operar, e outras opções. É particularmente
recomendado um comando como


que executará apenas os testes em `test/foo/bar_test.dart`,
e dentro desses apenas os testes com nomes correspondentes a `baz`.

Ao editar em uma IDE, a IDE deve fornecer exatamente o mesmo feedback
que o `flutter analyze` forneceria. Ao editar um arquivo de teste, a IDE também pode
executar testes individuais para você.
Veja a [documentação upstream sobre `flutter test`][flutter-cookbook-unit-tests].

[flutter-cookbook-unit-tests]: https://docs.flutter.dev/cookbook/testing/unit/introduction


## Notas

### Design de UI

Para issues que exigem construir nova UI, normalmente temos um
design no Figma que estará vinculado na descrição da issue.

Quando houver um design no Figma, um PR implementando a issue
deve corresponder exatamente ao design, exceto quando houver um
bom motivo para fazer algo diferente.
Como em qualquer diferença entre um PR e planos anteriores,
você deve [explicar a diferença](https://zulip.readthedocs.io/en/latest/contributing/reviewable-prs.html#explain-your-changes)
claramente na descrição do seu PR.

Para cores, espaçamentos (padding), tamanhos de fonte e detalhes de design semelhantes,
é raro haver um bom motivo para divergir do
design no Figma.
Ao [revisar seu trabalho](https://zulip.readthedocs.io/en/latest/contributing/reviewable-prs.html#review-your-own-work)
(o que você deve fazer antes de todo PR),
reserve um tempo para observar atentamente todos os detalhes do
design no Figma
e confirme que eles estão correspondidos no seu PR.

No nosso código, muitas cores e outros detalhes aparecem em `DesignVariables`
ou classes semelhantes como `ContentTheme`. Se você precisar de uma variável do Figma
que ainda não apareça no nosso código, por favor, adicione-a.


### Escrevendo testes

Escrevemos testes para todas as alterações no código Dart do aplicativo.
Como o Flutter e o Dart possuem excelentes recursos para testes, podemos escrever testes de forma eficiente, mesmo para tipos de código que frequentemente ficam sem testes: código de UI e código que faz solicitações de rede ou chama APIs externas.

Você pode, às vezes, encontrar código que não possui testes.
Geralmente, esse é um código da fase de protótipo inicial; quando fazemos alterações nele, escrevemos testes para essas mudanças e, muitas vezes, aproveitamos a oportunidade para escrever testes para a lógica já existente também.

Quando chegar a hora de escrever um teste, observe os testes existentes no mesmo arquivo de teste ou em nossos testes existentes para código semelhante, e siga os padrões que usamos ali. Notas sobre tipos específicos de testes:

 * Para código de UI, usamos a função padrão `testWidgets` do Flutter.
   Muitos widgets interagem com os dados do usuário; veja a documentação sobre
   nossos `TestZulipBinding` e `TestGlobalStore`, e os testes existentes que usam
   `testBinding.globalStore`, para saber como manipular dados de teste ali.

 * Para código que faz solicitações à API do Zulip, use `FakeApiConnection`;
   veja sua documentação e os testes existentes que o utilizam.

 * Para código que faz outras solicitações de rede, procure testes semelhantes já existentes;
   ou veja nosso `FakeHttpClient`, e use `withHttpClient` do `package:http` para fazer com que o código sob teste o utilize.

 * Para código que invoca plugins do Flutter ou chama APIs externas de outra forma,
   veja nossa classe `ZulipBinding`. Se não houver um membro existente nessa classe que envolva a API que você está usando, será necessário adicionar um; siga os exemplos existentes.


#### `check` vs. `expect`

Para nossos testes, usamos o [pacote `checks`][package-checks].
Este é um novo pacote da equipe do Dart, atualmente em prévia, e que está [destinado a substituir][package-checks-migration] o antigo pacote `matcher`.

Isso significa que, se você vir exemplos de código de teste em outro lugar que usem a função `expect`, preferimos traduzi-los para algo em termos de `check`.
Para obter ajuda com isso, veja o [guia de migração do `package:checks`][package-checks-migration] e a [documentação da API][package-checks-api] do pacote.

Como o `package:checks` ainda está em prévia, a equipe do Dart está aberta a feedback sobre a API em um grau que não estará mais quando atingir a versão 1.0.
Portanto, onde encontrarmos pontos problemáticos, agora é um bom momento para [relatá-los como issues][dart-test-tracker].

[package-checks]: https://pub.dev/packages/checks
[package-checks-api]: https://pub.dev/documentation/checks/latest/checks/checks-library.html
[package-checks-migration]: https://github.com/dart-lang/test/blob/master/pkgs/checks/doc/migrating_from_matcher.md
[dart-test-tracker]: https://github.com/dart-lang/test/issues


### Editando tipos de API

#### Compatibilidade com o servidor

Damos suporte ao Zulip Server 7.0 e versões posteriores.

Para recursos de API adicionados em versões mais recentes, use comentários `TODO(server-N)` (como os que você vê no código existente).


#### Exigir todos os parâmetros nos construtores de API

Em nossos tipos de API, os construtores geralmente devem evitar valores padrão para seus parâmetros, mesmo `null`.
Isso significa escrever, por exemplo, `required this.foo` em vez de apenas `this.foo`, mesmo quando `foo` é anulável.

Fazemos isso porque é comum, na API do Zulip, que um valor nulo ou ausente tenha um significado importante, e não um valor trivial apropriado para um padrão.
Assim, é melhor garantir que quem chama o construtor faça uma escolha explícita.

Se passar valores explícitos em testes for incômodo, uma função de fábrica em `test/example_data.dart` é uma forma adequada de compartilhar valores padrão.


#### Arquivos gerados

Ao editar qualquer uma das definições de tipo em nossa API, você precisará manter atualizado o código gerado correspondente (que lida com a conversão de JSON para e a partir de nossos tipos).

Para fazer isso, execute o seguinte comando:


### Suporte para desktop

Este aplicativo é destinado ao uso em plataformas móveis, especificamente
Android e iOS.

Em plataformas desktop, oferecemos suporte para executar o aplicativo durante o desenvolvimento,
mas não para uso geral. Em particular, isso significa:

 * O layout e a interface do usuário são projetados para dispositivos móveis.
   Não investimos tempo em adaptar o aplicativo para recursos ou paradigmas de interface desktop.

 * As integrações com plataformas externas (como abrir um link,
   tirar uma foto, etc.) são implementadas apenas para Android e iOS.
   Não investimos tempo em fazê-las funcionar em outras plataformas.

 * Por outro lado, o aplicativo é executável, e a funcionalidade principal funciona,
   pelo menos em Linux e macOS. Atualmente, nenhum colaborador regular
   o utiliza no Windows, mas aceitamos correções para mantê-lo funcionando lá também.

O motivo pelo qual oferecemos suporte para plataformas desktop é que,
para o desenvolvimento, às vezes é útil executar o aplicativo no desktop.
Por exemplo, isso facilita redimensionar a janela arbitrariamente,
o que pode ser útil para testar o comportamento do layout.


## Licença

Copyright (c) 2022 Kandra Labs, Inc. e colaboradores.

Licenciado sob a Licença Apache, Versão 2.0 (a "Licença");
você não pode usar este arquivo exceto em conformidade com a Licença.
Você pode obter uma cópia da Licença em:

    http://www.apache.org/licenses/LICENSE-2.0

A menos que exigido pela lei aplicável ou acordado por escrito, o software
distribuído sob a Licença é distribuído "NO ESTADO EM QUE SE ENCONTRA",
SEM GARANTIAS OU CONDIÇÕES DE QUALQUER TIPO, expressas ou implícitas.
Consulte a Licença para obter as permissões e limitações específicas
que regem o uso sob a Licença.

O software inclui alguns trabalhos lançados por terceiros sob outras
licenças livres e de código aberto. Esses trabalhos são redistribuídos
de acordo com os termos das licenças sob as quais foram recebidos.
