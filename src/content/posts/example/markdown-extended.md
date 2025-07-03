---
title: Markdown Extended Features
published: 2024-05-01
updated: 2024-11-29
description: "Read more about Markdown features in Fuwari"
image: ""
tags: [Demo, Example, Markdown, Fuwari, smilesDrawer]
category: "Examples"
draft: false
pinned: true
---

## GitHub Repository Cards

You can add dynamic cards that link to GitHub repositories, on page load, the repository information is pulled from the GitHub API.

::github{repo="Benzyl-titanium/fuwari"}

Create a GitHub repository card with the code `::github{repo="<owner>/<repo>"}`.

```markdown
::github{repo="Benzyl-titanium/fuwari"}
```

## Gitlab Repository Cards

::gitlab{repo="BianTaiLAB/NPSdose"}

Create a GitHub repository card with the code `::gitlab{repo="<owner>/<repo>"}`.

```markdown
::gitlab{repo="BianTaiLAB/NPSdose"}
```

## Admonitions

Following types of admonitions are supported: `note` `tip` `important` `warning` `caution`

:::note
Highlights information that users should take into account, even when skimming.
:::

:::tip
Optional information to help a user be more successful.
:::

:::important
Crucial information necessary for users to succeed.
:::

:::warning
Critical content demanding immediate user attention due to potential risks.
:::

:::caution
Negative potential consequences of an action.
:::

### Basic Syntax

```markdown
:::note
Highlights information that users should take into account, even when skimming.
:::

:::tip
Optional information to help a user be more successful.
:::
```

### Custom Titles

The title of the admonition can be customized.

:::note[MY CUSTOM TITLE]
This is a note with a custom title.
:::

```markdown
:::note[MY CUSTOM TITLE]
This is a note with a custom title.
:::
```

### GitHub Syntax

> [!TIP] > [The GitHub syntax](https://github.com/orgs/community/discussions/16925) is also supported.

```
> [!NOTE]
> The GitHub syntax is also supported.

> [!TIP]
> The GitHub syntax is also supported.
```

### smilesDrawer

```smiles
C(C1=CC=CC=C1)[Ti](CC1=CC=CC=C1)(CC1=CC=CC=C1)CC1=CC=CC=C1
```

````
```smiles
C(C1=CC=CC=C1)[Ti](CC1=CC=CC=C1)(CC1=CC=CC=C1)CC1=CC=CC=C1
```
````

<div class="smiles">C(C1=CC=CC=C1)[Ti](CC1=CC=CC=C1)(CC1=CC=CC=C1)CC1=CC=CC=C1</div>

```html
<div class="smiles">C(C1=CC=CC=C1)[Ti](CC1=CC=CC=C1)(CC1=CC=CC=C1)CC1=CC=CC=C1</div>
```

## size

```js
// public/js/chemdraw.js
const options = { width: 150, height: 150 };
```

## add script

```html
<script>
  if (window.renderSmiles) {
    setTimeout(window.renderSmiles, 100);
  }
</script>
```

<script>
  if (window.renderSmiles) {
    setTimeout(window.renderSmiles, 100);
  }
</script>
