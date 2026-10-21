# Qual carro você escolheria?

Mini game de duelos de carros, feito para celular. Escolha 1 de 2 carros; o carro escolhido enfrenta um novo concorrente da mesma classe, até sobrar um só.

As classes seguem as classes de veículos do GTA V: Compactos, Sedãs, SUVs, Cupês, Muscle, Clássicos esportivos, Esportivos, Super, Off-road e Vans.

## Arquivos

- `index.html`: o jogo inteiro.
- `carros.json`: sua lista de carros com fotos. Começa vazio (`[]`). Enquanto estiver vazio, o jogo usa a lista padrão, com ilustrações.
- `carros.exemplo.json`: exemplo do formato. Os nomes de arquivo dele são candidatos que não foram conferidos; o jogo confere sozinho.
- `LEIA-ME.md`: este texto. Não precisa subir no repositório.

## Publicar no GitHub Pages (pelo celular)

1. Abra o repositório `mount-your-carage` no navegador do celular, com a opção "Versão para computador".
2. Toque em **Add file → Upload files**, escolha `index.html` e `carros.json` e toque em **Commit changes**. Se já existirem arquivos com esses nomes, o GitHub os substitui.
3. Em **Settings → Pages**, a fonte deve ser **Deploy from a branch**, **main**, **/(root)**.
4. O jogo fica em `https://ferrazdeolinet.github.io/mount-your-carage/`. Depois de enviar, espere 1 a 2 minutos e recarregue.

## Como colocar carros específicos com foto

Você só informa o **nome do arquivo** da foto na Wikimedia Commons. Quando o jogo abre, ele consulta a Commons, confirma que o arquivo existe e traz a foto, o autor e a licença, que aparecem como crédito abaixo da foto. Se o arquivo não existir, o carro aparece com a ilustração, sem dar erro.

Edite o `carros.json` no GitHub (toque no arquivo, depois no lápis, cole o conteúdo novo e toque em **Commit changes**):

```json
[
  { "categoria": "super", "marca": "Audi", "modelo": "R8 V10 plus", "detalhe": "2018",
    "arquivo": "2018_Audi_R8_Coupe_V10_plus_Front.jpg" }
]
```

Campos:

- `categoria`, `marca`, `modelo` e `arquivo` são os principais. `detalhe` (geração e ano) é opcional.
- `categoria` aceita: `compactos`, `sedas`, `suvs`, `cupes`, `muscle`, `classicos`, `esportivos`, `super`, `offroad`, `vans`. Também aceita os nomes em inglês do GTA (compacts, sedans, coupes, sports classics, sports, super, off-road, vans).
- O nome do arquivo é o que aparece depois de `File:` na página da foto na Commons. Pode usar espaços ou underscores.
- Cada classe precisa de **pelo menos 4 carros** no arquivo para usar a sua lista. Com menos de 4, o jogo usa a lista padrão daquela classe.
- Opcional: `formato` (`hatch`, `sedan`, `suv`, `picape`, `esportivo`, `cupe`, `van`) e `cor` (ex.: `#c1272d`) controlam a ilustração usada quando não há foto.
- Se preferir informar tudo à mão, use `imagem` (link `https://`), `autor`, `licenca` e `fonte` no lugar de `arquivo`.

## Texto para pedir a lista a outra IA

> Monte um arquivo JSON (uma lista) com 6 a 10 carros reais para cada uma destas classes do GTA V: compactos, sedas, suvs, cupes, muscle, classicos, esportivos, super, offroad, vans. Cada item deve ter os campos: categoria, marca, modelo, detalhe (geração e ano, por exemplo "992 · 2019") e arquivo.
>
> "arquivo" é o nome exato de uma foto que existe na Wikimedia Commons (o que aparece depois de "File:" na página do arquivo), sem o prefixo "File:". Use só fotos que mostrem o carro inteiro, vistas de fora, e que identifiquem o modelo e a geração. Abra a página de cada arquivo antes de incluir. Não invente nomes: se não achar uma foto livre de um modelo, escolha outra geração ou outro carro. Responda somente com o JSON.

Não precisa conferir autor nem licença: o jogo busca isso sozinho.
