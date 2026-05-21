# IA Short Lab — OAuth Privacy Site

Páginas estáticas publicadas no GitHub Pages para satisfazer requisitos de Branding OAuth do Google Cloud Console (Application home page, Privacy policy URL, Terms of service URL).

Uso destinado exclusivamente à autenticação do aplicativo `IA Short Lab` contra YouTube Data API v3 no projeto `levanteande`. Não há serviço público hospedado.

## Conteúdo

- `index.html` — página inicial do app (Application home page).
- `privacy.html` — política de privacidade.
- `terms.html` — termos de uso.

## Publicação

1. Criar repositório público no GitHub (sugestão: `oscar-shorts-privacy`).
2. Subir os três arquivos HTML mais este `README.md` para a branch `main`.
3. Repositório → **Settings** → **Pages** → **Source**: `Deploy from a branch` → **Branch**: `main` / `(root)` → **Save**.
4. Aguardar ~1 minuto; URL final aparece no topo da página Pages.

## URLs esperadas

Substituir `<usuario>` pelo handle do GitHub do operador.

- Home: `https://<usuario>.github.io/oscar-shorts-privacy/`
- Privacy: `https://<usuario>.github.io/oscar-shorts-privacy/privacy.html`
- Terms: `https://<usuario>.github.io/oscar-shorts-privacy/terms.html`

## Aplicação no Google Cloud Console

Console → **Google Auth Platform** → **Branding** (`https://console.cloud.google.com/auth/branding?project=levanteande`):

- **Application home page** = URL home.
- **Application privacy policy link** = URL privacy.
- **Application terms of service link** = URL terms.
- **Authorized domains** = adicionar `github.io`.

Salvar, voltar em **Audience** e clicar **PUBLISH APP**.

## Manutenção

- Atualizar `Última atualização: DD/MM/AAAA` nos arquivos `privacy.html` e `terms.html` sempre que houver mudança real de escopo, contato ou retenção de dados.
- Manter contato do operador (`jefferson2459@gmail.com`) coerente em todas as páginas e no campo **Developer contact information** do Branding.
- Em caso de revogação de tokens em massa, instruir usuário a revisar https://myaccount.google.com/permissions.

## Escopo OAuth utilizado

`https://www.googleapis.com/auth/youtube.upload` — upload de vídeos via `videos.insert` para o canal autorizado.

## Limitações

- App permanece **Unverified** no Google até submissão e aprovação formal. Primeiro consent exibirá tela de aviso ("Google hasn't verified this app"); avançar manualmente.
- Sem verificação formal, cap de 100 usuários distintos autorizados continua valendo. Suficiente para uso pessoal.
- Refresh tokens deixam de expirar em 7 dias somente após `Publishing status = In production`.
