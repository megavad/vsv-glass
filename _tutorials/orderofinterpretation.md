---
title: Order of interpretation
author: tomjoht
date: 2017-01-29 21:45:03 -0800
---

Jekyll's main job is to convert your raw text files into a static website. It does this by rendering Liquid, Markdown, and other transforms as it generates the static HTML output.

In this conversion process, it's important to understand Jekyll's order of interpretation. By "order of interpretation," we mean what gets rendered, in what order, and what rules get applied in converting content.

If an element isn't converting, you can troubleshoot the problem by analyzing the order of interpretation.

## Order of interpretations

Jekyll converts your site in the following order:
