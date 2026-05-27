# Gerador de Assinatura - Santa Casa de Andradina

Site estático para gerar assinaturas de e-mail da Irmandade Santa Casa de Andradina e apoiar conferências internas da equipe de TI.

O projeto roda no GitHub Pages, não usa servidor próprio e integra as telas protegidas com Microsoft 365, Entra ID, Microsoft Graph e listas do SharePoint.

## Acesso

Produção:

```text
https://geradorassinatura.santacasaandradina.org/
```

GitHub Pages:

```text
https://kiwor101.github.io/Gerador-de-assinatura/
```

Repositório:

```text
https://github.com/kiwor101/Gerador-de-assinatura
```

## Páginas

`index.html`

Tela principal do gerador de assinatura.

`gerador-assinatura-santa-casa.html`

Cópia compatível da tela principal, mantida para links antigos.

`scripts-senhas.html`

Tela protegida por login Microsoft para script de comunicado, conferência de migração de e-mails e consulta de senhas internas.

`conferencia-ip-impressora.html`

Tela protegida por login Microsoft para conferir, adicionar, editar e excluir IPs de computadores e impressoras.

## Gerador de Assinatura

Recursos principais:

- Campos para nome, cargo, setor, ramal, e-mail e Teams.
- Domínio fixo para e-mail e Teams: `@santacasaandradina.org`.
- Telefone, site e endereço fixos da instituição.
- Logos salvas com prévia.
- Inclusão de logo por link público.
- Inclusão de logo por arquivo local apenas para teste.
- Exclusão de logos adicionadas pelo usuário.
- Presets de cores para campanhas ou ajustes visuais.
- Modelos para Outlook Classic e Outlook Web compacto.
- Cópia da assinatura pronta para colar no Outlook.
- Cópia ou download da assinatura como PNG.
- Modo claro e modo escuro apenas na interface.

O fundo da assinatura e da PNG gerada permanece branco mesmo com o modo escuro ativo.

## Logos

As logos fixas ficam em:

```text
assets/logos/
```

Para assinatura oficial no Outlook, prefira `Adicionar logo por link`, usando uma URL pública e direta da imagem.

O campo `Adicionar nova logo` usa arquivo local e serve apenas para teste no navegador. Ele não é recomendado para assinatura definitiva, porque o Outlook pode perder a imagem.

Sugestões gratuitas para gerar link público:

- [Imgur](https://imgur.com/upload)
- [ImgBB](https://imgbb.com/)
- [Postimages](https://postimages.org/)

## Outlook

`Copiar assinatura`

Recomendado para Outlook Classic. Copia a assinatura em HTML formatado.

`Copiar PNG`

Copia a assinatura como imagem, útil quando o Outlook Web altera espaçamentos do HTML.

`Baixar PNG`

Baixa a assinatura como arquivo de imagem.

## Área Protegida Microsoft

A barra superior possui login Microsoft. Após entrar, os links protegidos ficam disponíveis:

- `Emails`
- `Conferência`
- `Painel contas Microsoft`

Links públicos continuam disponíveis sem login:

- `Home`
- `Web Microsoft email`
- `Web Localweb email`

O botão `Sair da conta` limpa o login salvo no site e volta para a Home.

## SharePoint

Site usado:

```text
santacasaandradina.sharepoint.com/sites/IRMANDADEDASANTACASADEANDRADINA-TECNOLOGIADAINFORMAO
```

Listas usadas:

- `Controle Migracao Emails`
- `Script Migracao Email`
- `Conferencia ip e impressoras`

O usuário precisa ter permissão nessas listas para carregar e salvar dados.

## Emails

A tela `Emails` carrega a lista `Controle Migracao Emails`.

Campos usados:

- `EmailPrincipal`
- `EmailNovo`
- `Dono`
- `Concluido`

Funções:

- Pesquisar por e-mail ou dono.
- Marcar ou desmarcar item como concluído.
- Adicionar novo item.
- Consultar senha interna protegida por login.
- Copiar senha quando necessário.
- Editar o script padrão de comunicado.

As senhas não são lidas do SharePoint. Elas ficam em uma tabela interna do próprio arquivo `scripts-senhas.html` e são localizadas pelo valor de `EmailPrincipal`.

## Script de Comunicado

A tela `Emails` também carrega a lista `Script Migracao Email`.

O texto do comunicado é editável no site e salvo automaticamente no SharePoint.

## Conferência IP Impressora

A tela `Conferência` carrega a lista `Conferencia ip e impressoras`.

Campos usados:

- `Nome/Setor`
- `Ip Computador`
- `Impressora/Ip`

Funções:

- Pesquisar por nome, setor ou IP.
- Adicionar novo item.
- Editar item existente.
- Excluir item.
- Salvar alterações diretamente no SharePoint.

## Microsoft Entra

Aplicativo usado para login e Microsoft Graph:

```text
Gerador Assinatura Santa Casa
```

Permissões necessárias:

- `User.Read`
- `Sites.ReadWrite.All`

A permissão `Sites.ReadWrite.All` precisa de consentimento de administrador.

URLs de redirecionamento usadas:

```text
https://geradorassinatura.santacasaandradina.org/
https://geradorassinatura.santacasaandradina.org/scripts-senhas.html
https://geradorassinatura.santacasaandradina.org/conferencia-ip-impressora.html
https://kiwor101.github.io/Gerador-de-assinatura/
https://kiwor101.github.io/Gerador-de-assinatura/scripts-senhas.html
https://kiwor101.github.io/Gerador-de-assinatura/conferencia-ip-impressora.html
```

## Estrutura

```text
.
|-- .github/
|   `-- workflows/
|       `-- pages.yml
|-- assets/
|   |-- favicon.svg
|   `-- logos/
|-- importacao-microsoft-lists/
|   |-- configuracoes-gerador.csv
|   |-- configuracoes-gerador.xlsx
|   |-- controle-migracao-emails.csv
|   `-- controle-migracao-emails.xlsx
|-- .gitignore
|-- .nojekyll
|-- CNAME
|-- conferencia-ip-impressora.html
|-- gerador-assinatura-santa-casa.html
|-- index.html
|-- README.md
`-- scripts-senhas.html
```

## Publicação

O projeto está configurado para GitHub Pages.

Há um workflow em:

```text
.github/workflows/pages.yml
```

Ele publica o conteúdo estático da raiz do repositório no GitHub Pages.

O arquivo `CNAME` mantém o domínio personalizado:

```text
geradorassinatura.santacasaandradina.org
```

## Cuidados

- Não renomeie listas ou colunas do SharePoint sem ajustar o código.
- Não remova URLs de redirecionamento do Entra sem atualizar o login.
- Para logos oficiais, use sempre link público direto.
- Não coloque senhas no SharePoint se a regra for manter a consulta dentro do arquivo protegido do site.

## Direitos

Copyright © 2026 kiwors.
