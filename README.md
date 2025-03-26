# Hi 👋! I'm Naveen Bellamkonda, a Tech Entrepreneur 🚀

Welcome to my GitHub profile! I’m a **BBA Fintech** student at **Takshashila University**, and I’m passionate about using technology to drive impactful solutions in the business world. I'm on a continuous journey of learning and growing in the fields of **Business Analysis**, **Fintech**, and **Entrepreneurship**.

---

## 👨‍💻 About Me

- **Eager Learner**: Continuously expanding my knowledge in **Business Management**, **Business Analysis**, and **Fintech**. 📚
- **Project Enthusiast**: I love working on prototypes and projects that solve real-world problems. From **digital payment systems** to **business analysis tools**, I dive deep into bringing ideas to life. 💡
- **Public Speaker & Leader**: I enjoy leading teams, solving complex problems, and communicating effectively. 🎤
- **Creative Explorer**: Besides tech, I’m into **Taekwondo**, **painting**, **singing**, and **dancing** — hobbies that fuel my creativity and help me think outside the box! 🎨🎶

---

## 🔧 Technologies & Tools

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="30" alt="python logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" height="30" alt="mysql logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="30" alt="postgresql logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="30" alt="javascript logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="30" alt="git logo" />
</div>

---

## 📊 GitHub Stats

<div align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=NaveenFintech&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=NaveenFintech&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph" />
</div>

---

## 🔗 Connect with Me

<div align="left">
  <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="gmail logo" />
  <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="linkedin logo" />
  <img src="https://img.shields.io/static/v1?message=Twitter&logo=twitter&label=&color=1DA1F2&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="twitter logo" />
</div>

---

## 🎯 Current Projects

- **Digital Payment Prototype** 💳: A project to simplify and secure online payment systems.
- **Business Analysis Tools** 📊: Developing software tools that help organizations make smarter business decisions.
- **Entrepreneurial Ventures** 💡: Exploring new business ideas and products in the **Fintech** space.

---

## 🌱 What I'm Learning Right Now

- Improving my **Python** and **JavaScript** skills.
- Building more **data-driven applications** and learning more about **Machine Learning** and **AI**.
- Exploring the intersections of **Fintech** and **Blockchain** for business use cases.

---

## 🐍 GitHub Snake Animation

Check out my snake animation below! 🐍  
It represents my coding journey in a fun and interactive way!

<img align="right" height="150" src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExM3RxYWRjeDhpMTF5ZGhidDNyZml6bTUwemZyM2VuOWZqeTB1NWQycSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MPxg9U887PS0B8XT4J/giphy.gif" />

<br clear="both">
<img src="https://raw.githubusercontent.com/NaveenFintech/NaveenFintech/output/snake.svg" alt="Snake animation" />


name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark

      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
