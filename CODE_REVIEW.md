# Code Review — Livro de Receitas do Miguel

## Objetivo da revisão

Validar a versão final que será usada, baseada na V2.1 com Pages CMS, link direto para edição e Plano B JSON colapsado.

## Ficheiros revistos

```text
index.html
css/styles.css
js/app.js
data/recipes.json
.pages.yml
CMS_SETUP.md
README.md
assets/logo.svg
assets/default-recipe.svg
assets/photos/README.md
```

## Verificações automáticas executadas

### JavaScript

Foi executado:

```bash
node --check js/app.js
```

Resultado: sem erros de sintaxe.

### JSON

Foi executado:

```bash
python3 -m json.tool data/recipes.json
```

Resultado: JSON válido.

### YAML

O ficheiro `.pages.yml` foi carregado com parser YAML.

Resultado: YAML válido e com chaves principais `media`, `content` e `settings`.

### ZIP

Foi executado teste de integridade ao ZIP final.

Resultado: sem erros de compressão.

## Verificações de estrutura

- `index.html` referencia `css/styles.css` e `js/app.js`.
- `data/recipes.json` existe e contém 10 receitas.
- Todas as receitas têm ID único.
- Todas as receitas têm categoria válida:
  - `entradas`
  - `pratos-principais`
  - `sobremesas`
- Todas as receitas têm ingredientes e passos de preparação.
- Todas as classificações Miguelin estão entre 0 e 5.
- `assets/logo.svg` existe.
- `assets/default-recipe.svg` existe.
- `assets/photos/README.md` existe.
- `.pages.yml` existe na raiz do projeto.
- `CMS_SETUP.md` existe.

## Verificações funcionais

### Home

- Mostra o nome “Livro de Receitas do Miguel”.
- Mostra número total de receitas.
- Mostra pesquisa.
- Mostra filtros principais e botão para mais filtros.
- Mostra abas por categoria.

### Pesquisa

- A pesquisa mantém foco ao escrever.
- A pesquisa procura na receita completa, incluindo ingredientes, preparação, dicas, lista de compras e tags.

### Filtros

- Filtros por tags funcionam por seleção.
- Filtro por Miguelin mínimo está presente.
- Filtro por tempo máximo está presente.
- Existe opção para limpar filtros.

### Receita individual

- Mostra informação principal da receita.
- Mostra imagem real ou imagem padrão.
- Mostra ingredientes, dicas e preparação.
- Mantém modo cozinhar.
- Permite adicionar/remover da lista de compras.

### Lista de compras

- Junta ingredientes das receitas selecionadas.
- Remove duplicados simples.
- Agrupa por secções.
- Permite marcar itens como comprados.
- Aplica rasurado aos itens comprados.

### Adicionar receita

- Mostra Pages CMS como método recomendado.
- Tem botão direto para `https://app.pagescms.org/`.
- Tem ligação para `CMS_SETUP.md`.
- Mantém o gerador JSON como Plano B colapsado.

### Pages CMS

- `.pages.yml` configura media em `assets/photos`.
- `.pages.yml` configura `data/recipes.json` como ficheiro JSON em lista.
- Campos principais estão definidos no CMS.
- Campo `photo` está definido como imagem.

## Observações e limitações

- O site continua a ser estático. A gravação direta no GitHub é feita pelo Pages CMS, não pelo próprio site.
- O gerador JSON local continua disponível como fallback, mas ainda exige substituir `data/recipes.json` manualmente no GitHub.
- O agrupamento de lista de compras é heurístico. Funciona para os ingredientes atuais, mas pode precisar de afinação à medida que forem adicionadas muitas receitas novas.
- As tags no Pages CMS estão como lista de texto livre para permitir flexibilidade. Convém manter consistência nos nomes das tags.

## Conclusão

A versão final está apta para ser usada como versão principal. A arquitetura continua simples, compatível com GitHub Pages, e a integração com Pages CMS permite testar edição de receitas sem mexer diretamente nos ficheiros do GitHub.
