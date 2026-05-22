# Gerador de Assinatura - Santa Casa de Andradina

Gerador web simples para criar assinaturas de e-mail em HTML ou PNG para a Irmandade Santa Casa de Andradina.

O objetivo do projeto e facilitar a padronizacao das assinaturas dos colaboradores, mantendo telefone, site, endereco e identidade visual consistentes, mas permitindo alterar rapidamente nome, cargo, setor, ramal, e-mail, Teams, cores e logo.

## Acesso

GitHub Pages:

```text
https://kiwor101.github.io/Gerador-de-assinatura/
```

Arquivo local principal:

```text
index.html
```

## Recursos

- Campos editaveis para nome, cargo, setor, ramal, e-mail e Teams.
- Dominio fixo para e-mail e Teams: `@santacasaandradina.org`.
- Telefone, site e endereco fixos da instituicao.
- Biblioteca de logos com pre-visualizacao.
- Inclusao de logo por link publico.
- Inclusao de logo por arquivo local para teste.
- Exclusao de logos adicionadas pelo usuario.
- Presets de cores para uso normal ou campanhas.
- Modelos para Outlook Classic e Outlook Web compacto.
- Geracao de assinatura em HTML.
- Copia da assinatura pronta para colar no Outlook.
- Geracao e download da assinatura como PNG.
- Modo claro e modo escuro na interface do gerador.
- Pagina auxiliar de scripts e contas de e-mail.

## Como Usar

1. Abra o gerador.
2. Preencha os dados do colaborador.
3. Escolha uma logo salva ou adicione uma logo por link.
4. Ajuste as cores, se necessario.
5. Escolha o modelo de assinatura.
6. Use uma das opcoes de exportacao.

## Opcoes de Exportacao

`Copiar assinatura`

Recomendado para Outlook Classic. Copia a assinatura pronta com HTML formatado.

`Copiar HTML`

Gera o codigo HTML da assinatura para uso manual ou em ferramentas que aceitam HTML.

`Copiar como imagem PNG`

Copia a assinatura como imagem unica. E uma alternativa quando o Outlook Web altera o layout do HTML.

`Baixar imagem PNG`

Baixa a assinatura como imagem. Util quando o usuario prefere inserir a assinatura como arquivo de imagem.

## Logos

As logos fixas do projeto ficam em:

```text
assets/logos/
```

Para novas logos, existem dois caminhos:

- `Adicionar logo por link`: recomendado para uso real no Outlook. O link precisa ser publico e direto para a imagem.
- `Adicionar nova logo`: serve apenas para teste local no navegador.

Sites praticos para hospedar imagens gratuitamente:

- [Imgur](https://imgur.com/upload)
- [ImgBB](https://imgbb.com/)
- [Postimages](https://postimages.org/)

Depois do upload, copie o link direto da imagem e cole no campo `Adicionar logo por link`.

## Observacoes Sobre Outlook

O Outlook Classic costuma preservar melhor a assinatura em HTML.

O Outlook Web pode alterar espacamentos, largura ou alinhamento do HTML. Quando isso acontecer, use a opcao PNG para manter a assinatura visualmente fixa.

Se a logo nao aparecer no Outlook, confira se ela usa um link publico direto. Caminhos locais ou arquivos salvos apenas no navegador nao sao confiaveis para assinatura oficial.

## Modo Escuro

O modo escuro muda apenas a interface do gerador.

A assinatura, a pre-visualizacao e a PNG gerada continuam com fundo branco para evitar problemas de leitura e compatibilidade no e-mail.

## Scripts e Contas

A pagina `scripts-senhas.html` contem um texto padrao para comunicar mudanca de e-mail e uma tabela auxiliar de contas.

Por seguranca, senhas reais nao devem ser publicadas no GitHub Pages. Use um cofre de senhas ou controle interno autorizado para armazenar credenciais.

## Estrutura

```text
.
|-- index.html
|-- gerador-assinatura-santa-casa.html
|-- scripts-senhas.html
|-- assinatura-santa-casa.html
|-- assinatura-santa-casa-exemplo.html
|-- logo-santa-casa.png
|-- .nojekyll
`-- assets/
    `-- logos/
```

## Publicacao no GitHub Pages

1. Suba os arquivos para o repositorio.
2. Acesse `Settings` no GitHub.
3. Entre em `Pages`.
4. Selecione a branch principal e a pasta raiz.
5. Salve e aguarde a publicacao.

O arquivo `.nojekyll` foi incluido para garantir que o GitHub Pages sirva os arquivos estaticos sem processamento adicional.

## Direitos

Copyright (c) 2026 kiwors.
