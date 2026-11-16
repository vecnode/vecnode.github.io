---
layout: page
permalink: /research/
title: research
description: Peer-reviewed publications and conference proceedings.
# The page heading is `page.title`, which the navbar renders too, and the tab has to stay
# lowercase "research" to sit with the lowercase "about" tab. So the heading is capitalized
# at display level only: `_styles` is the theme's per-page <style> hook
# (_layouts/page.liquid), and `.post-title` appears nowhere else on this page.
_styles: >
  .post-title { text-transform: capitalize; }
nav: true
nav_order: 3
---

**Research Projects:**

- 111 Center: Human-AI Collaborative Design Center for International Cooperation and Disciplinary Innovation (B26063). Five year international collaboration project funded by the Chinese Ministry of Education (CN).

- Collections Transformer: PDRF extending "Transforming Collections: Reimagining Art, Nation and Heritage", 1 of 5 'Discovery Projects' part of the 5-year Towards A National Collection (TaNC) programme. Funded by UKRI's Arts and Humanities Research Council (AHRC). In partnership with Tate and Decolonising Arts Institute (AH/W003341/1).

- Charismatic Project: PDRF "AI-driven Storytelling for TV and Film Industries" led by Charismatic.AI, Channel 4, UAL Creative Computing Institute, Falmouth University, Aardman Animations, Sound Reactions and digital ethicist Lisa Talia Moretti, supported by InnovateUK (UKRI).

- Xperimus Project: AR “Experimentation in music in Portuguese culture: History, contexts and practices in the 20th and 21st centuries” (POCI-01-0145-FEDER031380) co-funded by the European Union through the Operational Program Competitiveness and Internationalisation, in its ERDF component, and by national funds, through the Portuguese Foundation for Science and Technology (FCT/PT).

**Programming Languages:** Python, C++, Rust, TS/JS, Docker, Shell.

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
