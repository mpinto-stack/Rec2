# Release Notes — Livro de Receitas do Miguel

## Versão final adotada — V2.1 + Pages CMS Link + YAML completo

Esta é a versão recomendada para usar. Junta o MVP estável, as melhorias de qualidade de vida da V2.1 e o fluxo de edição com Pages CMS.

### Destaques

- Site estático compatível com GitHub Pages.
- Receitas organizadas por **Entradas**, **Pratos principais** e **Sobremesas**.
- Pesquisa na receita completa.
- Filtros por tags, Miguelin mínimo e tempo máximo.
- Lista de compras combinada, agrupada por secções e com itens rasurados depois de comprados.
- Modo cozinhar com passos grandes para telemóvel.
- Imagem padrão para receitas sem foto real.
- Campo de foto preparado para `assets/photos/`.
- Página **Adicionar receita** com botão direto para Pages CMS.
- Gerador JSON mantido como **Plano B** colapsado.
- `.pages.yml` completo para Pages CMS.
- `CMS_SETUP.md` com instruções de teste e uso.

---

## Histórico de versões

### MVP inicial

- Criado o primeiro site estático em HTML, CSS e JavaScript.
- Receitas guardadas em `data/recipes.json`.
- Estrutura criada para GitHub Pages.
- Receitas extraídas e normalizadas a partir de `receitas.txt` e `tort.html`.
- Criadas categorias principais:
  - Entradas
  - Pratos principais
  - Sobremesas

### MVP com pesquisa e categorias

- Adicionada barra de pesquisa.
- Adicionados filtros/tags.
- Adicionadas abas por tipo de refeição.
- Criado sistema de cartões de receita.
- Criada página individual por receita.
- Criado modo cozinhar.
- Criada lista de compras combinada.

### Evolução visual

- Removidas estatísticas secundárias da home.
- Mantido apenas o número total de receitas.
- Texto inicial simplificado para “Resumo das receitas.”
- Adicionada navegação fixa inferior no mobile:
  - Receitas
  - Listas
  - Adicionar
- Criado logo simples em SVG.
- Criada imagem padrão para receitas sem foto.

### MVP v7 — versão estável

- Corrigido bug da pesquisa que perdia foco após escrever a primeira letra.
- Pesquisa passou a manter foco e cursor.
- Pesquisa expandida para procurar em:
  - título
  - categoria
  - resumo
  - dificuldade
  - doses
  - tempo
  - ingredientes
  - preparação
  - dicas
  - lista de compras
  - tags
- JSON e JavaScript validados.

### V2.1 — qualidade de vida

- Melhorado o editor local na página **Adicionar**.
- Possibilidade de editar receitas existentes.
- Possibilidade de duplicar receitas.
- Validação de campos obrigatórios.
- Pré-visualização antes de exportar.
- Exportação de receita individual em JSON.
- Exportação do `recipes.json` completo.
- Filtro por Miguelin mínimo.
- Filtro por tempo máximo.
- Lista de compras agrupada por secções:
  - Frescos / proteína
  - Congelados
  - Temperos / molhos
  - Mercearia
  - Frescos / legumes e fruta

### V2.1 + Pages CMS experimental

- Adicionado `.pages.yml` para testar Pages CMS.
- `data/recipes.json` configurado como ficheiro editável no Pages CMS.
- `assets/photos/` configurado como pasta de media.
- Campo `photo` configurado para imagem.
- Criado `CMS_SETUP.md`.

### V2.1 + Pages CMS Link

- Página **Adicionar receita** passou a privilegiar Pages CMS.
- Adicionado botão direto para abrir Pages CMS.
- Editor JSON antigo mantido como **Plano B**, mas colapsado.
- README atualizado com fluxo recomendado.
- `CMS_SETUP.md` atualizado.

### Correção final do `.pages.yml`

- Revisto o `.pages.yml` porque uma versão estava demasiado simplificada.
- Reposto `.pages.yml` mais completo, com:
  - descrições de campos
  - validação de `id`
  - categorias fixas
  - dificuldade como seleção
  - Miguelin 0 a 5
  - listas para ingredientes, preparação, dicas, compras e tags
  - campo de foto como imagem
  - configuração de media/fotos

### Revisão final

- Validado JavaScript com `node --check`.
- Validado `recipes.json` como JSON correto.
- Validado `.pages.yml` como YAML correto.
- Validada unicidade dos IDs das receitas.
- Validada presença dos ficheiros principais.
- Validada presença do link Pages CMS.
- Validado fallback/Plano B colapsado.
- ZIP final testado sem erros de compressão.

---

## Ficheiros principais

```text
index.html
css/styles.css
js/app.js
data/recipes.json
.pages.yml
CMS_SETUP.md
README.md
RELEASE_NOTES.md
PROJECT_HISTORY.md
CODE_REVIEW.md
assets/logo.svg
assets/default-recipe.svg
assets/photos/
```
