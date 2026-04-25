+++
date = '2026-04-22T21:19:13-04:00'
title = 'OSS Contributions'
weight = 1
+++

# OSS Contributions

### [chroma](https://api.github.com/repos/alecthomas/chroma) · ★4912 · `Go`
A general purpose syntax highlighter in pure Go 

<details>
<summary>
  <a href="https://github.com/alecthomas/chroma/pull/1247">fix: commenting issues on gas lexer</a> ·
  <code>PR</code> · <code>↑85 ↓3</code> ·
  <code>April 24, 2026</code>
</summary>

**Issues:** 447 1246   

<blockquote>

Fixes commenting issues in the GAS lexer and adds tests.

- Adds tests for `gas`
- Changes comment regex in 3 states: `directive-args`, `instruction-args`, `whitespace`

**Fixes #447**  
`@|!` - Adds comment prefixes
ARM  `@`
Motorola 68k `|`
SuperH `!`

**Fixes #1246**  
`\n` -> `\n?` - makes trailing newline optional so final-line comments are highlighted  
`.*?` -> `.*` - removed unnecessary lazy quantifier

<img width="751" height="304" alt="image" src="https://github.com/user-attachments/assets/9fd38bf2-6ee7-4656-9ecd-a161d57a7714" />


</blockquote>

<details>
<summary>Comments</summary>


`alecthomas`  
Thanks!

---


</details>
</details>




### [misp-docker](https://api.github.com/repos/MISP/misp-docker) · ★352 · `Shell`
A production ready Dockered MISP

<details>
<summary>
  <a href="https://github.com/MISP/misp-docker/pull/301">Add MISP-Guard container</a> ·
  <code>PR</code> · <code>↑251 ↓4</code> ·
  <code>September 17, 2025</code>
</summary>

**Issues:** 22   

<blockquote>

This PR adds MISP-Guard as an optional service.  
It's disabled by default but can be toggled with:
```
COMPOSE_PROFILES=misp-guard
```
Notes:
- Added the `entrypoint.sh` to the service so there was a way to dynamically target the `misp-core` container IP from docker's DNS.
- Opted for `depends_on` at misp-core start since I've had misp-core flap on first run.  
- `healthcheck` for misp-guard is set to `2m`, to avoid spamming the logs.
- The `README` has all the configuration is greater detail.

I've tested this extensively with clean builds, functions exactly as an external misp-guard would.  

Current dockerfile pulls misp-guard via git clone at build time, ideally this should be replaced with a published image and pinned version.

Fixes #22


</blockquote>

<details>
<summary>Comments</summary>


`ostefano`  
Love this!

May I suggest to also extend the GitHub actions so we build the image?

---

`monjiapawne`  
Thanks @ostefano, I've extended the test and release workflows to include misp-guard

---

`ostefano`  
Cool. Will merge as soon as I have a spare cycle to test it.

Thanks again!

---

`ostefano`  
I am doing a pass because as things they can not work (for example, they require cloning the repo for using it).

I will ask you to reivew it

---


</details>
</details>



<details>
<summary>
  <a href="https://github.com/MISP/misp-docker/pull/330">Add SES Configuration for SMTP</a> ·
  <code>PR</code> · <code>↑14 ↓0</code> ·
  <code>November 14, 2025</code>
</summary>

**Issues:**   

<blockquote>

Adds optional AWS SES SMTP variables to `docker-compose.yml`, based on implementation in [egos-tech/smtp](https://gitlab.com/egos-tech/smtp/-/blob/main/docker-compose.yml). 

Tested with SES in AWS and currently running in production.

</blockquote>

<details>
<summary>Comments</summary>



</details>
</details>



