# PsiGama

Página inicial de `psigama.com`: a iniciativa pessoal e aberta de software para pesquisa científica de Rogerio Cisi.

O site é só essa página: uma apresentação curta e um endereço de contato. Não há subpáginas nem build.

## Arquivos

| Arquivo | O que é |
| --- | --- |
| `index.html` | A página inicial, HTML estático |
| `css/psigama.css` | Os estilos da página |
| `favicon.svg` | O ícone do site |
| `CNAME` | O domínio próprio, criado pelo GitHub Pages |
| `.nojekyll` | Publica os arquivos como estão, sem passar pelo Jekyll |
| `LICENSE` | O texto da licença CC BY 4.0 |

## Publicação

No GitHub, em **Settings → Pages**, está escolhido **Deploy from a branch**, branch `main`, pasta `/ (root)`. A cada push na `main`, o site é publicado em `https://rogeriocisi.github.io/psigama/` e no domínio próprio, com **Enforce HTTPS** marcado.

> Não crie o arquivo `CNAME` antes de o domínio existir: com ele, o GitHub redireciona o site para um endereço que ainda não responde.

### DNS

| Nome | Tipo | Valor |
| --- | --- | --- |
| `psigama.com` | A | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (GitHub Pages) |
| `psigama.com` | AAAA | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` (GitHub Pages) |
| `www.psigama.com` | CNAME | `rogeriocisi.github.io` |

Os subdomínios do Crivo, `crivo.psigama.com` e `app.crivo.psigama.com`, ficam na mesma zona de DNS, mas são servidos e documentados pelo repositório [`crivo`](https://github.com/rogeriocisi/crivo).

## Licença

O conteúdo do site, textos e páginas, está sob a licença [Creative Commons Atribuição 4.0 Internacional (CC BY 4.0)](LICENSE), a mesma indicada no rodapé: pode ser compartilhado e adaptado, inclusive para fins comerciais, desde que se dê o crédito a Rogerio Cisi. O Crivo tem licença própria, a MIT, no repositório [`crivo`](https://github.com/rogeriocisi/crivo).
