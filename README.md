# Meu Pet

Jogo de pet virtual feito com a [VibeGameEngine](https://github.com/amatsuisoares/vibegameengine): um pet que nasce,
cresce e evolui em tempo real, com personalidade, desejos, memórias, vínculo com quem cuida e acontecimentos do dia a
dia. Sem morte; as notificações só contam o que o pet está fazendo. As funcionalidades estão em
[FEATURES.md](FEATURES.md).

## Como rodar

O jogo é um projeto da engine e roda **dentro** dela, na pasta `projects/`:

```bash
git clone https://github.com/amatsuisoares/vibegameengine.git
cd vibegameengine
npm install
git clone <url deste repositório> projects/meu-pet
npm run dev          # http://localhost:5173/?project=meu-pet
```

No VS Code com o Claude Code, o agente edita, joga e testa o jogo pelas tools `mcp__vibe__*` (ver o README da engine).

## Gerar o app

Na pasta da engine:

```bash
npm run vibe -- export meu-pet              # site estático em build/meu-pet/web
npm run vibe -- package desktop meu-pet     # Windows (.exe) em build/meu-pet/desktop/dist
npm run vibe -- package android meu-pet     # Android (.apk) em build/meu-pet/android
```

## Testes

`tests/meu-pet.test.ts` é o teste de regressão do jogo: roda junto com o `npm test` da engine sempre que o jogo está em
`projects/meu-pet`.

## Estrutura

```
project.json   nome, tamanho, assets, sons, ícone do app
scenes/        início, quarto, coleção e minigames
scripts/       comportamento do pet e da interface (JavaScript)
prefabs/       objetos criados durante o jogo
items/         comidas, brinquedos, camas e poções
assets/        sprites do pet e sons
playbooks/     roteiros de teste jogados pelo agente
tests/         teste de regressão (Vitest)
```
