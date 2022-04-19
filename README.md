# Anotações - Desafio Front-end Select Investimentos

Detalhes de componentes, correções e dúvidas. Como poderia melhorar?

## Definição dos Passos para Desenvolvimento

1. Navbar
2. Render lista de clientes - tabela
3. Consumo da API, render dinâmico de todos os clientes
4. Adição de filtros de pesquisa

## Observações e Dúvidas

### Estados

 - pageState: armazena qual página será renderizada no componente SectionRender
 - infoState/originalState: armazenam as informações dos clientes

### Padronização dos atributos

 - Começou a ficar complexo pensar em nomes diferentes para os atributos a cada nível em que um componente era chamado

### Navbar:

 - Componentizar melhor, separar em componentes menores
 - Âncora/Button, href ficou com link "vazio", entender quando deve-se mudar o link da página e quando deve-se fazer o re-render (pensando em uma SPA)
 - Não precisaria do React.Fragment, porque o return está envolvendo tudo com uma div semântica "nav"
 - Atributo "setInfoState" passado na chamada do Navbar pelo App.js não é necessário

 ### SectionRender:

 - Cria seção na página, área onde serão renderizados os conteúdos baseados no menu selecionado no Navbar
 - Verifica qual conteúdo será renderizado, componentes Investidores/Outras

 ### Outras: 

 - Renderiza uma imagem, simulando o conteúdo do menu
 - Também não precisaria do React.Fragment
 - Existe forma de import dinâmico? Uma maneira melhor para esse tipo de funcionalidade?

 ### Investidores:

 - Componentizar melhor
 - searchState/selectState: armazenam estados da barra de pesquisa e filtro de busca no Form. Poderia usar um único State!?
 - infoState é atualizada com a lista de informações filtradas pela pesquisa. Talvez essa variável não precise receber dados via API diretamente

 ### LinhasTabela:

 - É responsável por renderizar apenas o corpo da tabela de clientes
 - useEffect roda o seu conteúdo apenas uma vez (seu segundo parâmetro é um [] vazio)
 - A função getInfos não precisa de parâmetros, infoState não é utilizado e, além disso, ele poderia ser acessado sem ser passado como parâmetro para essa função
 - axios foi utilizado para o serviço API

## Questões Gerais

 - Até que ponto deve-se dividir o projeto em componentes menores?
 - Como definir padrões de projeto? Como o projeto deve ser estruturado, árvore de arquivos, nomenclaturas?
 - O mesmo vale para o Bootstrap. Qual a melhor prática pra integrá-lo com react?
 - Quando seria mais adequado utilizar o useContext ao invés de repassar variáveis de estados (useState) para os componentes?
 - Como definir quando deve ser feito um commit, nomenclatura, conteúdo e tamanho do texto complementar do commit?
 - Quando criar novas branches?
