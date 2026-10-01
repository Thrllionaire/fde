# Publishing

This course is a static HTML site published with GitHub Pages, from the `main`
branch root of `github.com/Thrllionaire/fde`. Mirrors the setup in
`../learnaiagents/PUBLISHING.md`.

## Two repos, one workspace

`/home/naren/dev/fde` holds two independent git repos:

- The **outer repo** (this directory, public) — tracks the published site:
  `lessons/`, `reference/`, `assets/`, `index.html`, `mission.html`,
  `resources.html`, `glossary.html`, `MISSION.md`, `RESOURCES.md`,
  `GLOSSARY.md`, `PUBLISHING.md`.
- The **inner repo**, rooted at `learning-records/` (private:
  `github.com/Thrllionaire/fde-progress`) — tracks `learning-records/*.md`
  and `practice/` (moved inside `learning-records/practice`, with a `practice`
  symlink at the workspace root so paths like `./practice/` still resolve).
  `NOTES.md` is untracked in both.

The outer repo's `.gitignore` excludes `/learning-records/`, `/practice`, and
`NOTES.md`, so `git add`/`git status` in this directory never touches the private
repo.

To commit progress (learning records, practice code):

```bash
cd /home/naren/dev/fde/learning-records
git add -A && git commit -m "..." && git push
```

The only build step is regenerating the three root markdown files to HTML whenever
they change:

```bash
cd /home/naren/dev/fde

md2html() {
  local src="$1" title="$2" out="$3" body
  body=$(pandoc "$src" -f markdown -t html)
  cat > "$out" <<HTML
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>${title}</title>
<link rel="stylesheet" href="assets/course.css">
</head>
<body>
<div class="wrap">

${body}

<footer class="colophon">
  <div class="nav-row">
    <a href="index.html">Course index</a>
    <a href="glossary.html">Glossary</a>
    <a href="resources.html">Resources</a>
    <a href="mission.html">Mission</a>
  </div>
</footer>

</div>
</body>
</html>
HTML
}

md2html MISSION.md   "Mission"   mission.html
md2html RESOURCES.md "Resources" resources.html
md2html GLOSSARY.md  "Glossary"  glossary.html
```

`NOTES.md` is teacher-only and is never rendered or published — it contains the answers to the
build tasks.

## Assets

`assets/course.css` is a fork of the AI Agents stylesheet with one deliberate change: the accent
is slate blue (`#1c5673` / `#6fb6d4`) rather than rust, so the two courses are distinguishable at
a glance. The widget contracts (`quiz.js`, `triage.js`, `rewrite.js`) are unchanged, so lessons
can be copied between workspaces. If a widget is improved in either workspace, port it to both.

## One-time setup (already done, for reference)

- `git init`, `gh repo create fde --public --source=. --remote=origin --push`
- `.nojekyll` added at repo root so GitHub Pages serves the HTML as-is instead of
  running it through Jekyll.
- Pages enabled via `gh api -X POST repos/Thrllionaire/fde/pages
  -f "source[branch]=main" -f "source[path]=/"`.
- Progress tracking split into a private repo: `practice/` moved into
  `learning-records/practice/`, a `practice` symlink added back at the workspace
  root, `learning-records/`, `practice`, and `NOTES.md` added to the outer
  `.gitignore`, then `git init` + `gh repo create fde-progress --private
  --source=. --remote=origin --push` run from inside `learning-records/`.
