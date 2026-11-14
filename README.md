# Psique Tecnologia Científica

Página inicial de `psique.tec.br`: a iniciativa pessoal e aberta de software para pesquisa científica de Rogerio Cisi.

## Estrutura do domínio

| Caminho | O que serve |
| --- | --- |
| `/` | Esta página (`index.html`, estática) |
| `/crivo` | Crivo, aplicação Spring Boot com `SERVER_SERVLET_CONTEXT_PATH=/crivo` |
| `/remoto` | Sistema Remoto (em desenvolvimento) |
| `/axion` | Axion (em breve) |

## Publicação

A página é um único arquivo HTML, sem build. Na VM, o Caddy serve este diretório na raiz e encaminha cada caminho de produto para a sua aplicação. Também pode ser publicada pelo GitHub Pages enquanto a VM não existe.

## A preencher

- Sinopse e previsão de lançamento de *O Sistema Psíquico*
- Link do canal *Vida Além da Matéria*
- Título da tese de doutorado e lista de artigos com links
