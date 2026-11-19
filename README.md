# PsiGama

Página inicial de `psigama.com`: a iniciativa pessoal e aberta de software para pesquisa científica de Rogerio Cisi.

## Estrutura

| Endereço | O que serve |
| --- | --- |
| `psigama.com/` | Página inicial (`index.html`) |
| `psigama.com/remoto` | Página explicativa do ReMoto (`remoto/index.html`). A nova versão do simulador está em desenvolvimento; a versão on-line da USP foi descontinuada |
| `psigama.com/axion` | Página explicativa do Áxion (`axion/index.html`), o próximo projeto |
| `psigama.com/quantum-study` | Página explicativa do Quantum Computing Study (`quantum-study/index.html`) |
| `psigama.com/crivo/air` | Experimentos de recepção anômala de informação do Crivo, P1-automático e P2-supervisionado (`crivo/air/index.html`) |
| `psigama.com/crivo/pes` | Testes de percepção extrassensorial do Crivo, P3-precognição e P4-visão-remota (`crivo/pes/index.html`). Os testes em si rodam na aplicação do Crivo, em `app.crivo.psigama.com/protocolo/P3` e `/protocolo/P4` |
| `psigama.com/crivo` | Página explicativa da plataforma Crivo (`crivo/index.html`): garantias, os quatro protocolos — dois experimentos e dois testes — e tecnologia |
| `psigama.com/sistema-psiquico` | Página do livro *O sistema psíquico* (`sistema-psiquico/index.html`), com o resumo em PDF (`sistema-psiquico/o-sistema-psiquico-resumo.pdf`), o link de compra na Amazon, o DOI do Zenodo e a capa (`sistema-psiquico/capa.jpg`) |
| `crivo.psigama.com` | Site estático do Crivo, com as páginas editoriais, publicado pelo GitHub Pages do repositório [`crivo`](https://github.com/rogeriocisi/crivo) a cada push na `main` (SPEC 0.21, seção 1.3). Um endereço que não existe ali vai para a aplicação |
| `app.crivo.psigama.com` | Aplicação Spring Boot do Crivo, na VPS: protocolos, contas, testes, estudos e carimbos, servida na raiz do subdomínio |

## Arquivos

- `index.html` e as páginas em `remoto/`, `axion/`, `quantum-study/`, `crivo/` (com `crivo/air/` e `crivo/pes/`) e `sistema-psiquico/` são HTML estático, sem build.
- O livro completo não é distribuído aqui: o eBook está no KDP Select, que exige exclusividade digital da Amazon. O registro do Zenodo (DOI 10.5281/zenodo.24370051) tem os arquivos restritos.
- `sistema-psiquico/o-sistema-psiquico-resumo.pdf` é gerado fora do repositório e entra aqui pronto; se o número de páginas mudar, ajuste a linha "Resumo: PDF, … páginas" em `sistema-psiquico/index.html`.
- `css/psigama.css` guarda os estilos compartilhados por todas as páginas.
- Os links entre as páginas são relativos, então o site funciona tanto em `rogeriocisi.github.io/psigama/` quanto no domínio próprio.

## Publicação

O site e o Crivo ficam em lugares separados: se a VM do Crivo cair, o site continua no ar.

### Site: GitHub Pages

1. No GitHub, em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`. A cada push na `main`, o site é publicado em `https://rogeriocisi.github.io/psigama/`.
2. Depois de registrar `psigama.com` num registrador de domínios `.com`, configure o DNS (veja abaixo) e informe o domínio em **Settings → Pages → Custom domain**. O GitHub cria o arquivo `CNAME` no repositório; marque **Enforce HTTPS** quando o certificado ficar pronto.

> Não crie o arquivo `CNAME` antes de o domínio existir: com ele, o GitHub redireciona o site para um endereço que ainda não responde.

### Crivo: VPS na Hostinger

- VPS KVM da Hostinger no data center de São Paulo, com Ubuntu 26.04, rodando a aplicação do Crivo com o PostgreSQL do sistema operacional, como pede a constituição do Crivo (sem Docker). O passo a passo está em [`docs/DEPLOY.md`](https://github.com/rogeriocisi/crivo/blob/main/docs/DEPLOY.md), no repositório `crivo`.
- O Caddy atende `app.crivo.psigama.com` com HTTPS automático e encaminha para a aplicação. Como ela fica na raiz do subdomínio, não é preciso context path.
- As páginas editoriais do Crivo não passam pela VPS: ficam em `crivo.psigama.com`, no GitHub Pages do repositório `crivo`.
- Backup diário do banco (`pg_dump`) para fora da VM, e envio de e-mail por um serviço SMTP externo.

### DNS

| Nome | Tipo | Valor |
| --- | --- | --- |
| `psigama.com` | A | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (GitHub Pages) |
| `psigama.com` | AAAA | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` (GitHub Pages) |
| `www.psigama.com` | CNAME | `rogeriocisi.github.io` |
| `crivo.psigama.com` | CNAME | `rogeriocisi.github.io` (GitHub Pages do repositório `crivo`) |
| `app.crivo.psigama.com` | A | IP público da VM do Crivo |

## Publicações

As publicações da página seguem o [Google Acadêmico](https://scholar.google.com/citations?user=a95TXg4AAAAJ&hl=pt-BR); ao atualizar a lista, confira também o [Currículo Lattes](http://lattes.cnpq.br/9619964316046037).

## Licença

O conteúdo do site, textos e páginas, está sob a licença [Creative Commons Atribuição 4.0 Internacional (CC BY 4.0)](LICENSE), a mesma indicada no rodapé: pode ser compartilhado e adaptado, inclusive para fins comerciais, desde que se dê o crédito a Rogerio Cisi. O Crivo tem licença própria, a MIT, no repositório [`crivo`](https://github.com/rogeriocisi/crivo).
