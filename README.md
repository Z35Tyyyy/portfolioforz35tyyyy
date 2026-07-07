# CyberPort

A cybersecurity portfolio with a fake terminal, a dinosaur, and a cat. One of these was necessary.

**Live:** [cyber-port-chi.vercel.app](https://cyber-port-chi.vercel.app)

## What is this

My personal portfolio and blog. I work in security, so naturally the website pretends to be a terminal instead of just showing you my projects like a normal person's site would.

## Architecture

Calling it "architecture" is generous, but here's what you're looking at:

- **One HTML file.** `index.html` is 1,843 lines long and contains the entire website — home, projects, about, blog — all of it. "Navigating" between pages means hiding the divs you're not looking at. Computer scientists call this a Single Page Application. I call it honesty.

- **Routing.** The nav links have real-looking hrefs and click handlers that immediately `preventDefault()`. The URL bar is decorative. The Back button works because I taught it to, manually, with `pushState`.

- **React, technically.** React 18 loads from a CDN and the JSX is compiled *in your browser, at runtime, on every single visit* by Babel Standalone. Your laptop is my build server. Thank you for your service.

- **A fake terminal** floating over a Three.js WebGL grid, because one rendering paradigm per page felt like quitting. It supports `whoami`, `ls`, `goto`, `theme`, `sudo`, and `hack`. `hack` does not hack anything. Neither do I, without a signed authorization letter.

- **The dinosaur.** Yes, that's the Chrome dino game. It runs from `dino.build.js`, a minified webpack bundle I extracted from a WordPress plugin. There is no source code. When the game needs changes, I edit the minified bundle by hand, like my ancestors did.

- **The blog** lives in a completely different repo and gets fetched from `raw.githubusercontent.com` at runtime. I built an entire CMS with a database, a markdown editor, and revision history — instead of just writing blog posts. This is called "engineering".

- **The theme toggle.** Dark/light mode, persisted to localStorage, with an inline script in `<head>` whose only job is to prevent a ~50ms white flash before the CSS loads. It is, without competition, the most rigorously engineered code on this site.

## Build & deploy

```
there is no build step
```

No `package.json`. No bundler. No tests. No linter. The build has never failed once.

On the bright side: no `node_modules`, no lockfile, no dependencies. You cannot have a supply-chain attack if you do not have a supply chain. As a security professional, I'm calling this a *hardening decision* and not what it actually is.

Deploys are `git push` → Vercel copies the files. It takes seconds, because there is nothing to do.

## Running locally

```
python -m http.server 8000
```

That's it. That's the whole DevOps.

## FAQ

**Why are there 2 MB of project screenshots sitting in the repository root?**
Because that's where I put them.

**Is the cat gif load-bearing?**
Yes.
