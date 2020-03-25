# Report of how we written our user guide: 

Editors:
- Ruihao/Homer li
- Dmitry Matiouchenko
---
Theme and style guide:
- Theme: Jekyll theme:  [just-the-doc](https://github.com/pmarsceill/just-the-docs).
- Style guide: [DigitalOcean](https://www.digitalocean.com/community/tutorials/digitalocean-s-technical-writing-guidelines)
---
Tools we used:
- Terminal
- Vscode
- Slack
- Zoom
---
Sources:
[tutorialspoint react setup](https://www.tutorialspoint.com/reactjs/reactjs_environment_setup.htm)
[React's official page](https://reactjs.org/)
---
## Why do we choose this topic for our guide?
Create-React-App abstracts the entire setup process and is too restrictive and bloated with extras files/folders.
It's important to be aware of the setup process to troubleshoot or customize the environment in the future.

---

## Why did we choose this theme and style guide?
We wanted a minimalistic and elegant looking Jekyll theme so we chose [just-the-doc](https://github.com/pmarsceill/just-the-docs) and found it to be simple to work with. We then chose [DigitalOcean](https://www.digitalocean.com/community/tutorials/digitalocean-s-technical-writing-guidelines) as our style guide since it seemed to be focused on comprehension for all levels of experience.

To use the theme we forked the themes repository from github and added our own content to it. We had to edit some of the configuration files as well.
The style guide was manually applied while writing the content of the guide.


---

## How did we collaborate during this time?

In the first couple of weeks, we were completing this guide face to face. Then the spring break came, we all agreed that we could just communicate through slack. However, due to the increasing case with COVID-19 we have to finish this guide remotely. Although we are using Github pages to build up our guide, the communication between us is still slower than face to face. Thankfully that we already discuss each person's role before the spring break come, so even we have to work remotely does not effect a lot of things.

---

## What are some things we learned while working on this guide?

- Using Jekyll themes.
- Writing markdown files.
- Forking github repositories and further collaboration through git.

One interesting technique we used in the guide is HTML image tags to serve the note/warning picture. The reason is that we can use a border to wrap around the picture and the text, visually it looks better.

---

## What are the difficulties we face when we are testing our guide, and how did we resolve that?

The significant difficulty is that most supporting instruction we are found for the installation section is outdated, and the instruction did not provide any of the troubleshooting guides. After hours of digging, we finally found the problem; the package used in the instructions is no longer supported. We updated all the packages to the supported ones and configured the whole thing again. We managed to solve the problem and get it working then had to rewrite the whole installation section.
