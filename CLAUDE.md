# PetHub Site - Guia do Projeto

## Sobre

Site estatico com "folders eletronicos" de produto: paginas que contam a
historia do produto, comparam com alternativas, etc. Acessadas via QR Code
impresso na loja (pet shop modular em container, franquia Pet 24/7 Market).
Repo irmao de `pethub` (negocio, dados financeiros) e `pethub/app` (Django,
catalogo e impressao de etiquetas).

## Por que este repo e separado

`pethub` e `pethub/app` tem dados sensiveis (financeiro, operacional). O
GitHub Pages so controla o que e publicado no site, nao a visibilidade do
repositorio — um repo publico expoe todos os arquivos pela aba de codigo,
nao so os servidos pelo Pages. Por isso este repo contem **apenas** conteudo
destinado ao publico. Nunca commitar dados financeiros/operacionais aqui.

## Estrutura

```
pethub-site/
├── marcas/
│   └── <slug-marca>.html
└── categorias/
    ├── racoes/
    ├── petiscos/
    ├── higiene/
    ├── cuidados/
    ├── brinquedos/
    └── acessorios/
        └── <slug-produto>.html
```

- `categorias/` usa os mesmos nomes de `catalogo.Categoria` no Django
  (`pethub/app/catalogo/models.py`), para manter site e catalogo alinhados.
  Categorias atuais: Racoes, Petiscos, Higiene, Cuidados, Brinquedos,
  Acessorios, Alimento. Nao existe "Medicamentos" (decisao consciente: pet
  shop nao vende medicamento).
- `marcas/` e independente do catalogo — nao ha campo de marca no modelo
  `Produto` ainda, entao paginas de marca sao mantidas soltas por agora.

## Conteudo das paginas

- Arte e conteudo produzidos no Canva (pela Bia, co-fundadora) e exportados
  para HTML/imagens aqui.
- Cada pagina de produto e o destino de um QR Code fisico na loja — o slug
  do arquivo deve ser estavel (nao renomear apos gerar/imprimir o QR Code).

## Hospedagem

GitHub Pages a partir da branch `main`. Ao decidir dominio custom, atualizar
este arquivo e o README com a URL final.

## Regras gerais

- Sempre propor um plano antes de escrever codigo.
- Uma tarefa por vez.
- Nao commitar nada que nao seja destinado ao publico (ver secao acima).
