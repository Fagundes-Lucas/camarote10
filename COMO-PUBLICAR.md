# Encerramento Camarote 10: como colocar no ar

São 3 arquivos que vão para o GitHub (`index.html`, `time.jpg`, `escudo.png`) e 1 que vai para o Google (`Code.gs`). Leva uns 15 minutos.

## Passo 1: planilha + Apps Script (onde ficam as respostas)

1. Cria uma planilha nova no Google Sheets chamada "Encerramento Camarote 10".
2. Menu **Extensões > Apps Script**. Apaga o que tiver no editor e cola o conteúdo de `Code.gs`. Salva (Ctrl+S).
3. No topo do editor, escolhe a função **setup** e clica em **Executar**.
   - O Google pede autorização: Revisar permissões > tua conta > **Avançado > Acessar (não seguro)** > Permitir. Esse aviso é normal porque o script é teu e não foi verificado pelo Google.
   - Volta na planilha: aparecem as abas **Respostas** e **Grade**.
4. **Implantar > Nova implantação** > engrenagem > **App da Web**:
   - Executar como: **Eu**
   - Quem pode acessar: **Qualquer pessoa** (sem isso os amigos não conseguem salvar)
5. Copia a URL que termina em `/exec`.

## Passo 2: colar a URL na página

Abre `index.html` num editor de texto, procura a linha abaixo e troca pelo teu link:

```js
const SCRIPT_URL = 'COLE_AQUI_A_URL_DO_APPS_SCRIPT';
```

Enquanto essa linha não for trocada, a página fica em **modo teste**: funciona, mas não salva nada.

## Passo 3: GitHub Pages (o link do grupo)

1. No GitHub: **New repository** com nome `camarote10`, **Public**.
2. **Add file > Upload files**: sobe `index.html`, `time.jpg` e `escudo.png` e faz o commit.
3. **Settings > Pages** > Source: *Deploy from a branch* > Branch **main** / **(root)** > Save.
4. Em 1 ou 2 minutos o link fica pronto: `https://SEU-USUARIO.github.io/camarote10/`

Opcional, para a foto aparecer na prévia do WhatsApp: no `index.html`, troca `content="time.jpg"` da tag `og:image` pelo link completo `https://SEU-USUARIO.github.io/camarote10/time.jpg`.

## Passo 4: testar antes de mandar

1. Abre o link no teu celular, escolhe "Lucas", marca uns dias e salva.
2. Confere a aba **Grade** da planilha: devem aparecer as tuas marcações coloridas.
3. Abre a aba **Resultado** na página: deve aparecer o ranking.

## Passo 5: mandar no grupo

> Fala, Camarote 10! Bora marcar o encerramento. Entra no link, toca no teu nome e marca os dias que tu pode, talvez pode ou não pode. Leva 1 minuto: https://SEU-USUARIO.github.io/camarote10/

## Pra mudar alguma coisa depois

- **Nomes, período, dias bloqueados ou jogos**: edita o `CONFIG` no topo do `Code.gs` e depois vai em **Implantar > Gerenciar implantações > lápis (Editar) > Versão: Nova versão > Implantar**.
- **Cuidado**: se usar "Nova implantação" em vez de editar a existente, o Google gera **outra URL** e a página para de salvar até tu colar a URL nova.
- Para apagar a resposta de alguém, é só deletar a linha da pessoa na aba **Respostas**.

## Como funciona o resultado

- Pode = 1 ponto, Talvez = 0,5, Não pode = 0.
- Empate: ganha o dia com menos "Não pode" e, se continuar empatado, a data mais cedo.
- Dias em branco de quem já respondeu aparecem como "Sem marcar".
- A aba Resultado se atualiza sozinha a cada 30 segundos.

Observação: GitHub Pages grátis exige repositório público. A foto do time fica acessível para quem tiver o link, mas não aparece em busca nenhuma.
