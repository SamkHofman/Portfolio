# Sam Hofman — Communications Portfolio

A static site. No build step, no server, no monthly cost. Content lives in six JSON
files in `/content`, which you edit through an admin panel in your browser.

```
index.html          the whole site (layout, styling, behaviour)
content/*.json      all the words and image references
images/             your photos, uploaded through the admin panel
.pages.yml          tells the admin panel what fields to show you
```

---

## Setup, once

**1. Put the folder on GitHub**

Create a free account at github.com. Make a new repository — call it `portfolio`,
set it to **Public**. On the empty repository page, choose "uploading an existing
file" and drag in everything from this folder.

One catch: `.pages.yml` starts with a dot, so your file browser may hide it. On Mac,
press `Cmd + Shift + .` in Finder to show hidden files before you drag.

**2. Put it online**

Go to netlify.com, sign in with GitHub, choose "Import an existing project", pick
your repository. Leave the build settings empty — there's nothing to build. Deploy.

You'll get an address like `sam-hofman.netlify.app`. If you want to keep
`samhofman-portfolio.com`, add it under Domain settings and point your domain there;
Netlify walks you through it.

**3. Connect the admin panel**

Go to app.pagescms.org, sign in with GitHub, and give it access to your `portfolio`
repository. It reads `.pages.yml` and builds the editor for you.

---

## Adding a new article, from then on

1. Open app.pagescms.org and pick your repository.
2. Click **Published work** in the sidebar.
3. Click **Add** at the bottom of the list of pieces.
4. Fill in title, year, your role, the link, a description, and drop in a thumbnail.
5. Save.

Netlify notices the change and republishes within about a minute. Same flow for
photography, events, research and the storytelling campaigns.

Bookmark app.pagescms.org — that's your whole workflow.

---

## Notes on the content

A few things carried over from the Canva version that need your attention:

- **Every `url` field is empty.** The Canva site's links didn't survive the export,
  so each piece currently shows "Link to be added". Paste the real URLs in and they
  become clickable.
- **Every image is a placeholder** — the striped blocks with captions. Upload the real
  files through the admin panel and they drop straight in.
- **The Myanmar coal plant article** was dated "20256" in the original. I've put 2026,
  since it's from the same series as the Laos piece. Change it if that's wrong.
- The Pride event had no year; I've assumed 2024.
- I fixed a handful of typos in the descriptions and changed "Communication's
  Portfolio" to "Communications Portfolio".

## If you want to edit the design

Everything visual is in the `<style>` block at the top of `index.html`. The colours
are named at the very top:

```css
--clay:   #c8b489   page background, carried over from your Canva site
--ink:    #17150f   near-black used for the hero and dark sections
--bone:   #f4efe2   text on dark
--river:  #2c5a61   deep teal, used for years and links
--marker: #e9c46a   the highlighter yellow
```

Change a value there and it updates everywhere.

## One thing to know about the built-in copy

`index.html` also contains a copy of the content inside a `<script id="seed">` block.
That's so the file still displays properly when opened directly from your computer,
before it's hosted anywhere. Once the site is live, the files in `/content` are what
it actually reads — the seed is only a fallback.
