# Olá, meu nome é Marcelo sou programador com foco em FrontEnd e prefiro trabalhar com React, Nextjs, React native, 
### já trabalhei em tempo integral como fullstack utilizando Laravel, Postgres, Vuejs.
[![Whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://api.whatsapp.com/send?phone=5575991674108&text=Recrutador)


<!-- ![MarceloFullStack GitHub stats](https://github-readme-stats.vercel.app/api?username=MarceloFullStack&show_icons=true&theme=dark&show_icons=true&include_all_commits=true&custom_title=MarceloFullStack&card_width=10) -->

<div >
<a href="https://marcelo-portifolio-nextjs.vercel.app/" target="_blank">
    <img style="width: 100vw" src="https://img2.picsize.com.br/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJrIjoidXBsb2Fkcy9jdXN0b21lci8xMTMyNi9zZWwtcGljdHVyZS82MDAzODMvMTExNTM2NTM5LzNiNWViZjZjNTQyMTRlMGFiMTg0MzFkNjBhNWZiNjA4LnBuZyIsImFjIjowLCJtVyI6MTM2NiwibUgiOjc2OH0.dKHDtBNY3vSoYFA6Wy7B-x3C1ohPzpGykLkb5iCzx2k"/>
</a>
</div>

### Técnologias que uso no dia a dia (Trabalho atual)

<div style="display: flex">

<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>


<img src="https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white"/>


<img src="https://img.shields.io/badge/react_native-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB"/>


<img src="	https://img.shields.io/badge/Redux-593D88?style=for-the-badge&logo=redux&logoColor=white"/>


<img src="https://img.shields.io/badge/TypeScript-20232A?            style=for-the-badge&logo=typescript&logoColor=white"/>


<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>


<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"/>


<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>

</div>
<br>

### Técnologias que já trabalhei (Antigos empregos)
<div style="display: flex">

<img src="https://img.shields.io/badge/vuejs-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D"/>


<img src="https://img.shields.io/badge/Vuetify-1867C0?style=for-the-badge&logo=vuetify&logoColor=AEDDFF"/>


<img src="https://img.shields.io/badge/laravel-%23FF2D20.svg?style=for-the-badge&logo=laravel&logoColor=white"/>


<img src="https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white"/>

</div>

# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: mishmanners
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

