---
name: deploy-pages
description: Publishes the app to GitHub Pages and checks the live page. Use only when the human asks to publish.
disable-model-invocation: true
---

# Publishing to GitHub Pages

**Commit, push to main, then open the live page and check it.**
Nothing red goes live, and nothing is pushed with --force.

Copy this checklist into your reply and tick it as you go:

- [ ] 1. Run bin/check and the tests in docs/testing.md. Anything red
         → stop and report; publish nothing.
- [ ] 2. Run git status. A file you did not expect, or anything with a
         password, key or token → stop and ask.
- [ ] 3. Commit with a message that says what changed, then
         git push origin main. Push rejected → report it; do not force.
- [ ] 4. Wait for the "pages build and deployment" run on GitHub
         (Actions tab, about a minute). Failed → report it and stop.
- [ ] 5. Open the live page: https://<user>.github.io/<repo>/login.html
         (there is no index.html at the root). It shows the old version
         → wait a minute and reload (back to 5). 404 → ask the human to
         check Settings › Pages: Deploy from a branch, main, / (root).
- [ ] 6. Check it like a user: the page and its CSS load, and one
         Behavior line from the spec works.
- [ ] 7. Report: the commit, the live address, what you checked.
