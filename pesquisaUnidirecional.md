## Soluções Open Source para Aplicativo de Avisos Unidirecionais

Este documento apresenta um conjunto de ferramentas open source analisadas com foco em aplicações de **avisos unidirecionais**, nas quais apenas o administrador pode publicar mensagens, e os usuários podem apenas ler (com possibilidade de marcar ciência). Os critérios levam em conta o funcionamento em **ambientes restritos como a intranet da Justiça Federal**, além da possibilidade de desenvolvimento de um aplicativo mobile personalizado (custom app).

---

### Introdução

A escolha da tecnologia para aplicativos de comunicação unidirecional deve considerar recursos como: envio exclusivo por administradores, controle de leitura (ciência), organização em grupos obrigatórios ou voluntários, segurança institucional (LDAP/SAML), operação offline ou em intranet e capacidade de personalização total via app próprio. Este documento compara opções open source com base nesses aspectos, usando uma classificação de 1 a 3 estrelas para os seguintes critérios:

* Complexidade
* Comunidade
* Curva de Aprendizado
* Suporte à Comunicação Unidirecional
* Compatibilidade com Intranet / Segurança Institucional

---

### Tecnologias Avaliadas

#### Custom App (React Native + Backend próprio)

* **Linguagem**: TypeScript (frontend), Java/Spring Boot (backend sugerido)
* **Integração**: controle total da lógica, interface, grupos obrigatórios, ciência e autenticação.
* **Uso Ideal**: Aplicativo personalizado com backend seguro operando em intranet, adaptado às regras institucionais.

#### Rocket.Chat

* **Linguagem**: Node.js, MongoDB
* **Integração**: API REST, suporte a LDAP/SAML, instalação em intranet.
* **Adaptação**: Canais read-only, bots para registrar ciência.
* **Uso Ideal**: Ambientes corporativos com controle de permissões e plugins customizados.

#### Matrix + Element

* **Linguagem**: Python (Synapse), React (Element)
* **Integração**: API REST e SDKs, possível instalação sem federação.
* **Adaptação**: Requer desenvolvimento de bot ou plugin para ciência.
* **Uso Ideal**: Casos onde segurança criptográfica é prioridade, com equipes técnicas disponíveis.

#### Zulip

* **Linguagem**: Python, React
* **Integração**: API REST e Web, instalação local.
* **Adaptação**: Requer adaptação de tópicos para emular avisos.
* **Uso Ideal**: Comunicação interna documentada, não para alertas diretos.

#### Mattermost

* **Linguagem**: Go
* **Integração**: API REST, LDAP/SAML, instalação on-premises.
* **Adaptação**: Canais com permissões restritas.
* **Uso Ideal**: Estrutura semelhante ao Slack com possibilidade de controle.

#### XMPP (ejabberd, etc.)

* **Linguagem**: Diversas (C, Erlang)
* **Integração**: via bibliotecas e plugins próprios.
* **Adaptação**: Comunicação unidirecional configurável via regras e extensões.
* **Uso Ideal**: Ambientes técnicos com alta necessidade de customização.

---

### Tabela Comparativa

| Solução                     | Complexidade | Comunidade | Curva de Aprendizado | Comunicação Unidirecional | Compatível com Intranet | Observações Relevantes                                                  |
| --------------------------- | ------------ | ---------- | -------------------- | ------------------------- | ----------------------- | ----------------------------------------------------------------------- |
| **Custom App (sob medida)** | ⭐⭐☆          | ⭐⭐⭐        | ⭐⭐☆                  | ⭐⭐⭐                       | ⭐⭐⭐                     | Total controle, ideal para regras de ciência e grupos obrigatórios.     |
| **Rocket.Chat**             | ⭐⭐☆          | ⭐⭐⭐        | ⭐⭐☆                  | ⭐⭐☆ *(com plugins)*       | ⭐⭐⭐                     | Requer configuração de permissões e bots para controle de leitura.      |
| **Matrix + Element**        | ⭐⭐⭐          | ⭐⭐⭐        | ⭐⭐☆                  | ⭐⭐☆ *(via bot)*           | ⭐⭐☆                     | Potente, mas exige ajustes para simplificação e operação sem federação. |
| **Zulip**                   | ⭐⭐☆          | ⭐⭐☆        | ⭐⭐☆                  | ⭐⭐☆ *(via adaptação)*     | ⭐⭐☆                     | Útil em cenários técnicos, mas menos direto para avisos institucionais. |
| **Mattermost**              | ⭐⭐☆          | ⭐⭐☆        | ⭐⭐☆                  | ⭐⭐☆ *(via restrições)*    | ⭐⭐⭐                     | Adequado com limitações de postagem para usuários.                      |
| **XMPP (ejabberd, etc.)**   | ⭐⭐⭐          | ⭐⭐☆        | ⭐☆☆                  | ⭐⭐☆ *(via extensões)*     | ⭐⭐⭐                     | Altamente customizável, mas exige configuração avançada.                |

---

### Considerações Finais

**Melhores Opções para a Justiça Federal:**

* **Custom App com backend próprio**: ideal para seguir exatamente as regras institucionais (avisos, ciência, grupos obrigatórios), funcionando offline ou em intranet, com integração LDAP ou OAuth.
* **Rocket.Chat**: solução adaptável via canais somente leitura e plugins, já validada por diversas instituições públicas.
* **Mattermost**: estrutura funcional para comunicação unidirecional com suporte a intranets e autenticação institucional.

**Alternativas Técnicas:**

* **Matrix + Element**: altamente seguro, mas demanda configuração para casos de uso simples.
* **XMPP**: ótimo para times com equipe técnica dedicada, mas com curva de implementação elevada.

A escolha deve refletir os critérios de segurança, controle da comunicação, rastreabilidade da ciência e compatibilidade com as diretrizes de infraestrutura da Justiça Federal.
