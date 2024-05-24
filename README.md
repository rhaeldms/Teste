# Adequação ou substituição do componente de editor do texto do modelo?

Atualmente existe um processo para implementar o ProseMirror no código atual com partes finalizadas e revisadas. Contudo existem algumas funcionalidades incompletas da tabela que necessitam de ajustes para implantação. Com as informações atuais descarta-se a substituição do componente de edição de tabela e acredita-se que o melhor ponto de partida seja adequar o componente atual referido na task #6.

Será necessário fazer teste dos códigos para identificar alguns problemas e pontos de melhoria que podem afetar seu funcionamento. Alguns pontos de observações:

 - Uso de Variáveis e Funções
 - Uso Inadequado de parâmetros
 - Problemas com Chaves (key) nos Loops
 - Componentes Customizados
 - Importação e Uso de Componentes e Dependências
 - Eventos e Manipulação do DOM
 - Funcionalidades de Botões

 **Localização do Editor no Código:** pjemaisr\src\components\AppEditor\Editor.ts
  - Arquivo principal do editor: `Editor.ts`
  - Template Vue: `AppEditor.vue`

## Referências:

 - [Documentação do ProseMirror](https://prosemirror.net/docs/ref/#commands)
 - [Propriedades Vue.js](https://br.vuejs.org/v2/guide/components-props.html)
 - [Aplicação de Vue.js](https://www.alura.com.br/artigos/cuidados-com-o-estado-de-uma-aplicacao-vue)
 - [Manipulação de Evento Vue.js](https://pt.vuejs.org/guide/essentials/event-handling)
