# Teste Pages CMS — Livro de Receitas do Miguel

Esta versão inclui configuração experimental para editar receitas através do Pages CMS.

## O que foi adicionado

- `.pages.yml` na raiz do repositório.
- Configuração para editar o ficheiro `data/recipes.json` como uma lista de receitas.
- Configuração de media para fotos em `assets/photos/`.
- Campo de foto ligado ao CMS.

## Como testar

1. Carrega esta versão para o GitHub.
2. Confirma que o ficheiro `.pages.yml` está na raiz do repositório.
3. Vai a `https://app.pagescms.org/`.
4. Faz login com GitHub.
5. Dá acesso ao repositório do site de receitas.
6. Abre a coleção **Receitas**.
7. Edita uma receita existente ou cria uma nova.
8. Guarda/publica a alteração.
9. Aguarda o GitHub Pages atualizar o site.

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
- Se adicionares tags novas, é melhor também adicioná-las à lista de opções no `.pages.yml` para aparecerem no CMS.

## Limitação desta abordagem

Esta configuração edita o mesmo `data/recipes.json` que o site já usa. Isto é bom porque não obriga a mudar a arquitetura do site.

A confirmação final será feita depois de testar no Pages CMS real, porque a interface pode depender das validações atuais do serviço.
