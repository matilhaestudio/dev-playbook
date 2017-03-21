# Front end Playbook 

## Organização de arquivos
Siga esta estrutura abaixo para organizar os estilos do projeto:

```
|- stylesheets/main.scss // import all style files
|- stylesheets/globals
|  _transitions.scss
|  _colors.scss
|  _fonts.scss
|  _spacing.scss
|  _type.scss
|  _buttons.scss
|  _forms.scss
|- stylesheets/components
|  _header.scss
|  _footer.scss
|  _calendar.scss
|- stylesheets/modules
|  _dashboard.scss
|  _clients.scss
|  _orders.scss
|- stylesheets/vendor
|  bootstrap.scss
```

## Formatação
- Use a sintaxe SCSS para escrever SASS.
- Use hífen quando for nomear mixins, extends, classes, functions & variables.
  - Ex: `span-columns` e não `span_columns` ou  `spanColumns` 
- Use um espaço entre o valor e a propriedade
  - `width: 20px` e não `width:20px` 
- Use uma linha em branco entre seletores.
- Use hex color sempre que possível: #FFF
- Evite usar propriedades abreviadas para apenas um valor.
  - `background-color: #ff0000;` e não `background: #ff0000;` 
- Use `// comment`  ao invés de  `/* */` para blocos de comentário.
- Sempre use um espaço entre o seletor e `{` .
- Use sempre aspas duplas.
- Sempre escreva em letras minúsculas, exceto em cores hex ou strings.
- Não coloque unidade depois do 0 (zero), a não ser que seja requisito de um mixin.
- Coloque o zero em números decimais: `0.5 em` e não `.5 em` 
- Sempre deixe um espaço entre operandos: 
  - `$variable * 1.5` e não  `$variable * 1.5` 
- Evite operações em propriedades abreviadas:
  - Ex `padding: $variable * 1.5 variable * 2` 
- Use parenteses entre operações individuais em propriedades abreviadas:
  - Ex:  `padding: ($variable * 1.5) ($variable * 2);` 
- Use % para determinar o peso em funções de cor no SASS: 
  - `darken($color, 20%)` e não `darken($color, 20)` 

## Outros
- Use ordem alfabética para declarações;
- Coloque `@extends`  e  `@includes`  no topo da lista de declarações;
- Coloque seletores concatenados em segundo;
  - Ex: `h1.page-title` 
- Coloque pseudo-states and pseudo-elements em terceiro.
  - Ex: `&:before {}` 
- Coloque nested elements em quarto.
- Coloque nested classes em quinto.
- Coloque media queries no final da lista de declarações.

## Seletores
- Não use ID's.
- Use nomes significativos e fáceis de entender: 
  - Ex: `$visual-grid-color` e não `$color` ou `$vslgrd-clr`.
- Escreva o nome das classes de maneira mais objetiva possível. Nem muito pequena, nem muito grande.
- Evite usar seletores de descendente direto:
  - Ex: `article > h1` 
- Evite nesting com mais de 3 níveis de profundidade.
- Use HTML tags on vague classes that need a qualifier like header.application not .main.
- Evite usar tags HTML no nome da classe: 
  - Ex: `section.news` e não `section.news-section` 
- Evite usar tags HTML em marcações genéricas:
  - Ex `.widgets` e não `div.widgets`.
- Evite usar tags HTML em classes com nomes muito especificos como `.featured-articles`.
- Evite nesting dentro de media queries.

## Outras considerações

- Use Normalize para manter consistência entre browsers.
- Use a estrutua HTML para ordenar os seletores do arquivo. Não vá colocando seletores um em baixo do outro.
- Evite ter arquivos com mais de 100 linhas.


Feito com base no playbook da [Thoughtbot](https://github.com/thoughtbot/guides/)
