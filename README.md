# PsiGama

Página inicial de `psigama.tec.br`: a iniciativa pessoal e aberta de software para pesquisa científica de Rogerio Cisi.

## Estrutura

| Endereço | O que serve |
| --- | --- |
| `psigama.tec.br/` | Página inicial (`index.html`) |
| `psigama.tec.br/remoto` | Página explicativa do ReMoto (`remoto/index.html`). A nova versão do simulador está em desenvolvimento; a versão on-line da USP foi descontinuada |
| `psigama.tec.br/axion` | Página explicativa do Áxion (`axion/index.html`), o próximo projeto |
| `psigama.tec.br/quantum-study` | Página explicativa do Quantum Computing Study (`quantum-study/index.html`) |
| `psigama.tec.br/pes` | Testes de percepção extrassensorial (`pes/index.html`). Os testes em si rodam no Crivo, em `crivo.psigama.tec.br/testes/...` |
| `crivo.psigama.tec.br` | Crivo, aplicação Spring Boot do repositório [`crivo`](https://github.com/rogeriocisi/crivo), servida na raiz do subdomínio |

## Arquivos

- `index.html` e as páginas em `remoto/`, `axion/`, `quantum-study/` e `pes/` são HTML estático, sem build.
- `css/psigama.css` guarda os estilos compartilhados por todas as páginas.
- Os links entre as páginas são relativos, então o site funciona tanto em `rogeriocisi.github.io/psigama/` quanto no domínio próprio.

## Publicação

O site e o Crivo ficam em lugares separados: se a VM do Crivo cair, o site continua no ar.

### Site: GitHub Pages

1. No GitHub, em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`. A cada push na `main`, o site é publicado em `https://rogeriocisi.github.io/psigama/`.
2. Depois de registrar `psigama.tec.br` no registro.br, configure o DNS (veja abaixo) e informe o domínio em **Settings → Pages → Custom domain**. O GitHub cria o arquivo `CNAME` no repositório; marque **Enforce HTTPS** quando o certificado ficar pronto.

> Não crie o arquivo `CNAME` antes de o domínio existir: com ele, o GitHub redireciona o site para um endereço que ainda não responde.

### Crivo: VM na Oracle Cloud (Always Free)

- VM Arm (Ampere A1) com Linux, na região de São Paulo ou Vinhedo, rodando a aplicação do Crivo com o PostgreSQL do sistema operacional, como pede a constituição do Crivo (sem Docker). O passo a passo da aplicação está no repositório `crivo`.
- Um proxy reverso (por exemplo, o Caddy) atende `crivo.psigama.tec.br` com HTTPS automático e encaminha para a aplicação. Como o Crivo fica na raiz do subdomínio, não é preciso context path.
- Backup diário do banco (`pg_dump`) para fora da VM, e envio de e-mail por um serviço SMTP, porque a porta 25 vem bloqueada.

### DNS

| Nome | Tipo | Valor |
| --- | --- | --- |
| `psigama.tec.br` | A | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (GitHub Pages) |
| `psigama.tec.br` | AAAA | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` (GitHub Pages) |
| `www.psigama.tec.br` | CNAME | `rogeriocisi.github.io` |
| `crivo.psigama.tec.br` | A | IP público da VM do Crivo |

## Publicações

As publicações da página seguem o [Google Acadêmico](https://scholar.google.com/citations?user=a95TXg4AAAAJ&hl=pt-BR); ao atualizar a lista, confira também o [Currículo Lattes](http://lattes.cnpq.br/9619964316046037).
