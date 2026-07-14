# Teste Pages CMS — Livro de Receitas do Miguel

Esta versão inclui configuração experimental para editar receitas através do Pages CMS.

## O que foi adicionado

- `.pages.yml` na raiz do repositório.
- Configuração para editar o ficheiro `data/recipes.json` como uma lista de receitas.
- Configuração de media para fotos em `assets/photos/`.
- Campo de foto ligado ao CMS.

## Fluxo recomendado

1. No site, abre **Adicionar receita**.
2. Clica em **Abrir Pages CMS**.
3. Faz login com GitHub, se necessário.
4. Escolhe o repositório do site de receitas.
5. Entra na coleção **Receitas**.
6. Edita uma receita existente ou cria uma nova.
7. Guarda/publica a alteração.
8. Aguarda o GitHub Pages atualizar o site.

## Atalho dentro do site

Na página **Adicionar receita** existe um botão direto para abrir o Pages CMS. O editor JSON antigo continua disponível como plano B, mas fica colapsado para não atrapalhar o fluxo normal.

## Como adicionar fotos pelo Pages CMS

1. No campo **Foto**, escolhe ou envia uma imagem.
2. A imagem fica em `assets/photos/`.
3. O campo `photo` da receita deverá ficar com um caminho tipo:

```text
assets/photos/nome-da-receita.jpg
```

Se a foto ficar vazia, o site usa automaticamente:

```text
assets/default-recipe.svg
```

## Regras importantes

- O campo `id` deve ser único.
- O campo `id` deve usar apenas letras minúsculas sem acentos, números e hífens.
- Exemplo correto: `arroz-frito-camarao`.
- Não uses espaços no `id`.
- As tags podem ser escritas livremente, mas convém manter tags consistentes com as que já existem.

## Nota técnica

O Pages CMS edita o mesmo `data/recipes.json` que o site já usa. Isto evita alterar a arquitetura do site e mantém o GitHub Pages simples.
