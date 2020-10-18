###  Thais Denise Espínola :octocat:

<!--
**Thairocine/Thairocine** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 Eu gosto de café e aprender novas coisas ...
- 🌱 Atualmente estou aprendendo Python...
- 👯 Faço parte de comunidades como o Elas@Computação e Pyladies Paraíba ...
- 🤔 Eu amo trabalhar em equipe e conhecer novas pessoas.
- 💬 No meu tempo livre amo assistir Netflix, ler e conversar
- 📫 Instagram : @thais.espinola_
- 😄 Pronomes: Ela / Dela
- ⚡ Amo uma conversa contagiante! 
-->
- 🔭 Eu gosto de café e aprender novas coisas :coffee:
-  :computer: Atualmente estou aprendendo Python 
- 👯 Faço parte de comunidades como o Elas@Computação e Pyladies Paraíba :hearts:
- 🤔 Eu amo trabalhar em equipe e conhecer novas pessoas.
- 💬 No meu tempo livre amo assistir Netflix, ler e conversar
- 📫 Instagram : @thais.espinola_
- 😄 Pronomes: Ela / Dela
- ⚡ Amo uma conversa contagiante! 
- :headphones: Amo música!
 
 Thais Denise Espínola :octocat: (English version) 
 - 🔭 I like coffee and learn new things :coffee:
- :computer:I'm currently learning Python ...
- 👯 I am part of communities like Elas @ Computação and Pyladies Paraíba ...
- 🤔 I love working as a team and meeting new people.
- 💬 In my spare time I love watching Netflix, reading and chatting
- 📫 Instagram: @ thais.espinola_
- 😄 Pronouns: She / Her
- ⚡ I love a contagious conversation!
-: headphones: I love music! 

name: Generate Theme Readme

on:
  push:
    branches:
      - master
    paths:
      - "themes/index.js"

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v1
      - name: setup node
        uses: actions/setup-node@v1
        with:
          node-version: "12.x"

      - name: npm install, generate readme
        run: |
          npm install
          npm run theme-readme-gen
        env:
          CI: true

      - name: Run Script
        uses: skx/github-action-tester@master
        with:
          script: ./scripts/push-theme-readme.sh
        env:
          CI: true
          PERSONAL_TOKEN: ${{ secrets.PERSONAL_TOKEN }}
          GH_REPO: ${{ secrets.GH_REPO }}

