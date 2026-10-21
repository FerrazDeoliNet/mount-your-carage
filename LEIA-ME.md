# Qual carro você escolheria?

Mini game de duelos de carros, feito para celular. Escolha 1 de 2 carros; o carro escolhido enfrenta um novo concorrente da mesma categoria, até sobrar um só.

## Arquivos

- `index.html`: o jogo inteiro (não precisa de mais nada para rodar).
- `carros.json`: sua lista de carros com fotos. Começa vazio (`[]`). Enquanto estiver vazio, o jogo usa a lista padrão com ilustrações.

## Publicar no GitHub Pages (pelo celular)

1. Abra o repositório `mount-your-carage` no navegador do celular (github.com).
2. Toque em **Add file** e depois em **Upload files**. Escolha `index.html` e `carros.json` e toque em **Commit changes**. Os dois precisam ficar na pasta principal, não dentro de outra pasta.
3. Vá em **Settings**, depois **Pages**. Em **Source**, escolha **Deploy from a branch**. Em **Branch**, escolha **main** e a pasta **/(root)**, e toque em **Save**.
4. Espere alguns minutos. O endereço do jogo será `https://ferrazdeolinet.github.io/mount-your-carage/`.

Se o menu Settings não aparecer, abra o github.com no navegador com a opção "Versão para computador".

## Como colocar carros específicos com foto

Edite o `carros.json` no GitHub (toque no arquivo, depois no lápis, cole o conteúdo novo e toque em **Commit changes**). Cada carro é um item da lista:

```json
[
  {
    "categoria": "esportivo",
    "marca": "Porsche",
    "modelo": "911 GT3 RS",
    "detalhe": "992 · 2023",
    "imagem": "https://commons.wikimedia.org/wiki/Special:FilePath/NOME_EXATO_DO_ARQUIVO.jpg?width=900",
    "autor": "Nome do fotógrafo",
    "licenca": "CC BY-SA 4.0",
    "fonte": "https://commons.wikimedia.org/wiki/File:NOME_EXATO_DO_ARQUIVO.jpg"
  }
]
```

Regras:

- `categoria` aceita: `hatch`, `sedan`, `suv`, `picape`, `esportivo`, `eletrico`. Outro nome cria uma categoria nova.
- Cada categoria precisa de **pelo menos 4 carros** no arquivo para usar a sua lista. Com menos de 4, o jogo usa a lista padrão daquela categoria.
- `marca`, `modelo` e `categoria` são obrigatórios. `detalhe` (geração e ano) é opcional.
- `imagem` precisa começar com `https://`. Se o link estiver quebrado, o jogo mostra a ilustração no lugar, sem dar erro.
- `autor`, `licenca` e `fonte` são opcionais, mas as licenças da Wikimedia Commons exigem dar o crédito. O jogo mostra o autor e a licença abaixo da foto, e na tela final o crédito vira um link para a página da foto.
- Opcional: `formato` (`hatch`, `sedan`, `suv`, `picape`, `esportivo`) e `cor` (ex.: `#c1272d`) controlam a ilustração usada quando não há foto.

Depois de salvar o arquivo no GitHub, o jogo leva de 1 a 2 minutos para mostrar a mudança. Se não aparecer, recarregue a página.

## Texto para pedir a lista a outra IA

> Monte um arquivo JSON (uma lista) com 10 a 12 carros para cada uma destas categorias: hatch, sedan, suv, picape, esportivo, eletrico. Cada item deve ter os campos: categoria, marca, modelo, detalhe (geração e ano, por exemplo "992 · 2023"), imagem, autor, licenca e fonte.
>
> A imagem deve ser um arquivo que realmente existe na Wikimedia Commons, no formato `https://commons.wikimedia.org/wiki/Special:FilePath/NOME_EXATO_DO_ARQUIVO.jpg?width=900`. A fonte é a página do arquivo, no formato `https://commons.wikimedia.org/wiki/File:NOME_EXATO_DO_ARQUIVO.jpg`. Autor e licença devem ser os que aparecem nessa página.
>
> Use só fotos que mostrem o carro inteiro, vistas de fora, e que identifiquem o modelo e a geração. Não invente nomes de arquivo. Se não achar uma foto livre de um modelo, troque por outra geração. Responda somente com o JSON.

Confira alguns links antes de publicar: abra a `fonte` de cada carro e veja se a foto é mesmo daquele modelo. Outras IAs costumam errar nomes de arquivo.
