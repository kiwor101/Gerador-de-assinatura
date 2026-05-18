# Gerador de Assinatura - Santa Casa de Andradina

Gerador simples de assinaturas de e-mail em HTML e PNG para a Irmandade Santa Casa de Andradina.

O projeto foi criado para facilitar a padronizacao das assinaturas dos usuarios, permitindo alterar dados do colaborador, escolher logos, ajustar cores e gerar uma assinatura pronta para colar no Outlook.

## Recursos

- Campos para nome, cargo, setor, ramal, e-mail e Teams.
- Dominio fixo para e-mail e Teams: `@santacasaandradina.org`.
- Telefone, site e endereco fixos da instituicao.
- Biblioteca de logos com pre-visualizacao.
- Upload de novas logos com nome personalizado.
- Exclusao de logos adicionadas pelo usuario.
- Presets de cores:
  - Padrao
  - Azul
  - Azul escuro
  - Azul claro
  - Vermelho
  - Verde agua
  - Dourado preto
- Geracao da assinatura em HTML.
- Geracao da assinatura como imagem PNG.
- Versoes para Outlook Classic e Outlook Web compacto.

## Como usar

Abra o arquivo:

```text
index.html
```

Ou acesse pelo GitHub Pages:

```text
https://kiwor101.github.io/Gerador-de-assinatura/
```

Preencha os campos, escolha a logo e as cores desejadas, depois use uma das opcoes:

- `Copiar assinatura`: recomendado para Outlook Classic.
- `Copiar HTML`: para ferramentas que aceitam codigo HTML.
- `Copiar como imagem PNG`: alternativa para Outlook Web.
- `Baixar imagem PNG`: recomendado quando o Outlook Web desconfigurar o HTML.

## Observacoes sobre Outlook

O Outlook Classic costuma preservar melhor o HTML da assinatura.

O Outlook Web pode alterar a largura e quebrar o layout do HTML. Quando isso acontecer, use a opcao de imagem PNG para manter o visual padronizado.

## Estrutura

```text
.
├── index.html
├── gerador-assinatura-santa-casa.html
├── assinatura-santa-casa.html
├── assinatura-santa-casa-exemplo.html
├── logo-santa-casa.png
└── assets/
    └── logos/
```

## Logos

As logos fixas ficam em:

```text
assets/logos/
```

Logos enviadas pelo upload ficam salvas no armazenamento local do navegador. Para uma logo ficar disponivel para todos via GitHub Pages, adicione o arquivo em `assets/logos/` e registre a logo na lista do gerador.

## Publicacao

Para publicar no GitHub Pages:

1. Suba os arquivos para o repositorio.
2. No GitHub, acesse `Settings`.
3. Entre em `Pages`.
4. Selecione a branch principal e a pasta raiz.
5. Salve e aguarde a publicacao.

O arquivo `.nojekyll` foi incluido para garantir que o GitHub Pages sirva os arquivos estaticos sem processamento adicional.
