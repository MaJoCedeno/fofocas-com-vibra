# Fofocas com Vibra | Gerador de Sessões

Este repositório contém o template, o script e a documentação usados para
criar as páginas interativas das aulas de português conversacional do
projeto **Fofocas com Vibra** (Associação VIBRA).

Cada sessão gerada é um único ficheiro HTML autocontido — sem servidor, sem
instalações — com vocabulário interativo, expressões, adivinhas, um baralho
de perguntas de conversa, curiosidades culturais e trabalho de casa. Tudo com
as cores, tipografia e logótipos oficiais da VIBRA.

---

## Estrutura do repositório

```
fofocas-com-vibra-skill/
├── SKILL.md                              — instruções completas de uso (ver abaixo)
├── assets/
│   ├── template.html                     — template HTML reutilizável
│   ├── fofoca-com-vibra-logo.png         — logótipo do programa (fundo transparente)
│   ├── vibra-logo.png                    — logótipo da Associação VIBRA (fundo transparente)
│   └── example-content-sessao3.json      — exemplo completo e funcional (Sessão 3: Profissões)
├── scripts/
│   └── build_session.py                  — script que junta conteúdo + template = página final
└── references/
    ├── content-schema.md                 — formato técnico do ficheiro de conteúdo
    └── ficha-de-conteudo.md              — ficha em português simples, para preencher sem código
```

---

## Como usar — Opção A: com a funcionalidade de Skills do Claude

Se a vossa organização tiver acesso a Skills instaláveis no Claude, basta
carregar o ficheiro `fofocas-com-vibra-skill.skill` (gerado a partir desta
pasta) nas definições da organização. Depois disso, qualquer pessoa da
equipa só precisa de escrever, numa conversa nova:

> "Cria uma sessão Fofocas com Vibra sobre [tema]"

e o Claude usa automaticamente este template, sem precisar de mencionar o
GitHub nem colar ficheiros.

## Como usar — Opção B: sem Skills, direto a partir deste repositório

O Claude não acede sozinho a este repositório: só lê o que alguém colar ou
ligar explicitamente numa conversa. Para gerar uma sessão nova:

1. **Preenche a ficha** em [`references/ficha-de-conteudo.md`](references/ficha-de-conteudo.md)
   com o conteúdo da sessão (vocabulário, expressões, adivinhas, perguntas,
   curiosidades, trabalho de casa).
2. Numa conversa com o Claude, cola:
   - o link deste repositório (ou os ficheiros `template.html` e
     `build_session.py` diretamente, se o Claude tiver uma ferramenta de
     leitura de repositórios ligada), **e**
   - a ficha preenchida.
3. Anexa também os dois ficheiros de logótipo (`fofoca-com-vibra-logo.png` e
   `vibra-logo.png`) diretamente na conversa — links para imagens no GitHub
   nem sempre são lidos corretamente pelo Claude, por isso é mais seguro
   anexá-los.
4. Pede: **"gera a página no formato Fofocas com Vibra com este conteúdo,
   usando o template e o script deste repositório"**.

O Claude vai construir o ficheiro de conteúdo (JSON), correr o script
`build_session.py`, e devolver o HTML final pronto a descarregar.

---

## Documentação de referência

- [`SKILL.md`](SKILL.md) — regras de marca, estrutura fixa das 7 secções,
  fluxo de trabalho completo (é a fonte de verdade sobre como cada sessão
  deve ser construída).
- [`references/content-schema.md`](references/content-schema.md) — formato
  técnico exato do JSON que o script espera.
- [`references/ficha-de-conteudo.md`](references/ficha-de-conteudo.md) —
  versão em português simples da mesma ficha, para preencher sem
  conhecimentos técnicos.

---

## Regras de marca (não alterar sem combinar com a equipa)

- **Cores:** roxo `#7046B6`, laranja `#FF6736`, amarelo `#FDC848`, fundo
  creme `#FBF6EC` (retiradas do Brand Book oficial da VIBRA).
- **Tipografia:** Livvic (títulos) e Quicksand (texto corrido).
- **Logótipos:** sempre os dois, no cabeçalho e no rodapé.
- **Instagram:** rodapé liga sempre a `@vibra.associacao`.
- Sem travessões (—) nem pontos separadores (·) em texto visível — usar
  vírgulas, dois pontos ou o carácter `|`.
- **Nunca reproduzir letras de música completas** — só título, artista e uma
  justificação breve.
- **Estrutura fixa de 7 secções**, sempre pela mesma ordem: Aquecimento,
  Vocabulário, Expressões, Adivinhas, Conversa, Curiosidades, Trabalho de
  casa.

---

## Partilhar uma sessão já gerada

- **Rápido, para a aula:** enviar o ficheiro HTML por WhatsApp ou email —
  abre em qualquer navegador, sem internet.
- **Link permanente:** arrastar o ficheiro para [app.netlify.com/drop](https://app.netlify.com/drop).
- **Site do curso, com todas as sessões:** publicar os ficheiros HTML neste
  mesmo repositório e ativar o GitHub Pages, para ficarem todos acessíveis
  num único URL que cresce a cada sessão.
