# PsiGama

Página inicial de `psigama.tec.br`: a iniciativa pessoal e aberta de software para pesquisa científica de Rogerio Cisi.

## Estrutura do domínio

| Caminho | O que serve |
| --- | --- |
| `/` | Página inicial (`index.html`, estática) |
| `/crivo` | Crivo, aplicação Spring Boot com `SERVER_SERVLET_CONTEXT_PATH=/crivo` (repositório `crivo`) |
| `/remoto` | Página explicativa do ReMoto (`remoto/index.html`). A nova versão do simulador está em desenvolvimento; a versão on-line da USP foi descontinuada |
| `/axion` | Página explicativa do Áxion (`axion/index.html`), o próximo projeto |
| `/quantum-study` | Página explicativa do Quantum Computing Study (`quantum-study/index.html`) |
| `/pes` | Testes de percepção extrassensorial (`pes/index.html`). Os testes rodam no servidor do Crivo, em `/crivo/testes/...` |

## Arquivos

- `index.html` e as páginas em `remoto/`, `axion/`, `quantum-study/` e `pes/` são HTML estático, sem build.
- `css/psigama.css` guarda os estilos compartilhados por todas as páginas.

## Publicação

Na VM, o Caddy serve este diretório na raiz e encaminha `/crivo` para a aplicação. Também pode ser publicado pelo GitHub Pages enquanto a VM não existe.

As publicações da página seguem o [Google Acadêmico](https://scholar.google.com/citations?user=a95TXg4AAAAJ&hl=pt-BR); ao atualizar a lista, confira também o [Currículo Lattes](http://lattes.cnpq.br/9619964316046037).
