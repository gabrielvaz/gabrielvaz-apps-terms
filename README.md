# gabrielvaz-apps-terms

Site público com o **suporte** e os **documentos legais** dos aplicativos de
Gabriel Kruschewsky Mattos Vaz. Publicado pelo GitHub Pages a partir da branch
`main`, pasta raiz (`/`).

URL: <https://gabrielvaz.github.io/gabrielvaz-apps-terms/>

## Estrutura

```
index.html          Índice dos apps (EN, PT-BR, ES)
lorcanapp/
  index.html        Home do LorcanApp: download, suporte e contato
  privacy.html      Política de Privacidade
  terms.html        Termos de Uso
.nojekyll           Serve os arquivos como estão, sem processar com Jekyll
```

Cada app novo entra numa pasta própria (`/<slug-do-app>/`) e ganha uma linha no
`index.html` da raiz.

## Regras destas páginas

As lojas abrem estas URLs no celular do revisor. Por isso:

- HTML estático puro: **sem JavaScript** e **sem recurso externo** (nada de CDN,
  fonte remota, `<script>` ou `<link>` para fora). Todo o CSS é embutido.
- Os três idiomas (EN, PT-BR, ES) convivem no mesmo arquivo; o seletor de idioma
  são apenas âncoras.
- Sem login e sem geobloqueio.
- Toda página traz nome do app, titular, data de atualização, contato e o aviso
  de não afiliação com Disney/Ravensburger nos três idiomas.

## LorcanApp: a fonte do conteúdo é o app

O texto da Política de Privacidade e dos Termos de Uso é **materialmente
idêntico** ao exibido dentro do app, em Ajustes › Sobre e Legal.

- Fonte de verdade: `lib/features/legal/legal_content.dart` no repositório do
  app (`gabrielvaz/lorcana-app`).
- Cópia derivada, usada para gerar estas páginas: `docs/` naquele repositório.

Se o texto legal mudar no app, ele precisa ser republicado aqui. Divergência
entre a política web e a in-app é motivo de rejeição na App Store.

## Como sincronizar depois de uma mudança no app

1. Ajuste `lib/features/legal/legal_content.dart` no repositório do app.
2. Atualize `docs/privacy.html` e `docs/terms.html` naquele repositório com o
   mesmo teor.
3. Copie os arquivos para cá, dentro de `lorcanapp/`:
   ```bash
   cp ../lorcana-app/docs/privacy.html ../lorcana-app/docs/terms.html lorcanapp/
   ```
4. Reponha o rodapé das duas páginas: aqui não existe `support.html` (a home
   acumula o suporte) e há um link a mais para `../` (índice dos apps).
5. Atualize a data de "última atualização" nas três páginas do app.
6. `git commit` e `git push`. O Pages republica em cerca de um minuto.

## URLs usadas nas lojas

| Campo | URL |
| --- | --- |
| Support URL | `https://gabrielvaz.github.io/gabrielvaz-apps-terms/lorcanapp/` |
| Privacy Policy URL | `https://gabrielvaz.github.io/gabrielvaz-apps-terms/lorcanapp/privacy.html` |
| License Agreement / EULA | `https://gabrielvaz.github.io/gabrielvaz-apps-terms/lorcanapp/terms.html` |
