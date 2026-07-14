# Histórico de pedidos e implementação — Livro de Receitas do Miguel

Este ficheiro resume o que foi pedido ao longo do projeto e como cada pedido foi implementado.

## 1. Criar site pessoal de receitas

### Pedido
Criar um site pessoal simples para receitas, gratuito, alojado em GitHub Pages, com receitas organizadas por entradas, pratos principais e sobremesas.

### Implementação
Foi criado um site estático em HTML, CSS e JavaScript, com dados guardados em `data/recipes.json`. A estrutura é compatível com GitHub Pages, sem backend nem base de dados.

---

## 2. Compilar receitas dos ficheiros enviados

### Pedido
Usar `receitas.txt` e `tort.html` para extrair e normalizar receitas, sem obrigatoriamente usar o HTML antigo como base.

### Implementação
As receitas foram extraídas, limpas e normalizadas para um formato comum em JSON, com campos como nome, categoria, doses, tempo, dificuldade, Miguelin, ingredientes, preparação, dicas, compras, tags e foto.

---

## 3. Definir método de adicionar receitas

### Pedido
Pensar na melhor forma de adicionar receitas sem custos.

### Implementação
Inicialmente foi criada uma página **Adicionar** que gera JSON para copiar ou descarregar. Depois foi criada a versão V2.1 com editor melhorado e exportação do `recipes.json` completo. Finalmente foi adicionada integração experimental com Pages CMS.

---

## 4. Pesquisa e filtros

### Pedido
Criar barra de pesquisa, idealmente por ingredientes, e filtros simples.

### Implementação
A pesquisa foi implementada em JavaScript e procura na receita completa: título, resumo, ingredientes, preparação, dicas, compras, tags, tempo, doses e dificuldade. Foram adicionados filtros por tags, Miguelin mínimo e tempo máximo.

---

## 5. Visual simples e moderno

### Pedido
Visual moderno, não exagerado, com logo simples e ícones, sem imagens reais inicialmente.

### Implementação
Foi criada uma interface leve, mobile-first, com cartões, abas e cores quentes. O logo foi simplificado várias vezes até ficar em formato SVG simples. Também foi criada uma imagem padrão `assets/default-recipe.svg` para receitas sem foto real.

---

## 6. Mobile e modo cozinhar

### Pedido
O site seria usado sobretudo no telemóvel para consultar receitas e teria utilidade um modo cozinhar.

### Implementação
Foi adicionada navegação inferior fixa no mobile e um modo cozinhar com passos grandes, avançar, retroceder e fechar.

---

## 7. Lista de compras

### Pedido
Criar lista de compras por receita e lista combinada, com possibilidade de riscar itens comprados e evitar duplicados.

### Implementação
A lista combinada usa as receitas selecionadas, remove duplicados simples, permite marcar itens como comprados e aplica rasurado. Na V2.1 passou a agrupar por secções: frescos/proteína, congelados, temperos/molhos, mercearia e frescos/legumes/fruta.

---

## 8. Classificação Miguelin

### Pedido
Adicionar classificação de 1 a 5 estrelas “Miguelin”.

### Implementação
Foi criado o campo `miguelin` em cada receita. A classificação aparece nos cartões e página individual. Também foi adicionado filtro por Miguelin mínimo.

---

## 9. Fotos

### Pedido
Deixar espaço para fotos e explicar como adicionar.

### Implementação
Cada receita tem o campo `photo`. Se estiver vazio, o site usa `assets/default-recipe.svg`. Para foto real, a imagem deve ir para `assets/photos/` e o campo `photo` deve conter o caminho, por exemplo `assets/photos/arroz-frito-camarao.jpg`.

---

## 10. Pages CMS

### Pedido
Testar Pages CMS para evitar editar manualmente o GitHub.

### Implementação
Foi criado `.pages.yml` na raiz do projeto, configurando `data/recipes.json` como lista editável e `assets/photos/` como media. Foi criado `CMS_SETUP.md` com instruções.

---

## 11. Link direto para Pages CMS no site

### Pedido
Como o Pages CMS agradou, simplificar o fluxo colocando o link diretamente na página **Adicionar receita**, mantendo o gerador JSON como alternativa.

### Implementação
A página **Adicionar receita** passou a mostrar primeiro o botão **Abrir Pages CMS**. O gerador JSON ficou colapsado como **Plano B**, disponível caso o Pages CMS falhe.

---

## 12. Revisão final e documentação

### Pedido
Fazer uma revisão completa ao código, acrescentar release notes e histórico do que foi pedido/feito.

### Implementação
Foram adicionados:

- `RELEASE_NOTES.md`
- `PROJECT_HISTORY.md`
- `CODE_REVIEW.md`

Também foi feita validação técnica final ao JavaScript, JSON, YAML, estrutura do projeto e ZIP.
