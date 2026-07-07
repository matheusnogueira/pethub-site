# PetHub Site

Paginas eletronicas de produto para o PetHub (pet shop modular em container,
franquia Pet 24/7 Market). Cada pagina conta a historia do produto, faz
comparacoes com concorrentes/alternativas, etc. Sao acessadas pelo cliente
dentro da loja via QR Code impresso na etiqueta/gondola.

## Por que um repo separado

O sistema interno do PetHub (`pethub/app`, Django) e o repo de negocio
(`pethub`, com planilhas financeiras) contem dados sensiveis. O GitHub Pages
publica um site publico a partir de um repositorio, mas **nao restringe a
visibilidade do restante do repo** — se o repo for publico, qualquer pessoa
pode navegar em todos os arquivos pela aba de codigo do GitHub, nao so no
que o Pages serve. Por isso este site fica em um repositorio proprio,
contendo apenas conteudo destinado ao publico.

## Conteudo

- Design das paginas (arte, fotos, textos) e produzido pela Bia (esposa,
  co-fundadora) no Canva e exportado para ca.
- Categorias seguem a mesma taxonomia do catalogo Django
  (`catalogo.Categoria` em `pethub/app`), para manter consistencia entre o
  sistema interno e o site publico.

## Estrutura

```
pethub-site/
├── marcas/                # paginas institucionais por marca (ex: historia da marca)
│   └── <slug-marca>.html
└── categorias/             # paginas de produto, uma por categoria do catalogo
    ├── racoes/
    ├── petiscos/
    ├── higiene/
    ├── cuidados/
    ├── brinquedos/
    └── acessorios/
        └── <slug-produto>.html
```

## Hospedagem

GitHub Pages, publicado a partir da branch `main` (raiz ou `/docs`, a
definir ao ativar o Pages nas configuracoes do repo). URL de cada pagina e
o alvo do QR Code impresso para o produto correspondente.
