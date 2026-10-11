# eruto-skills marketplace

18 plugins for Codex and Claude Code, published by the [eruto-skills organization](https://github.com/eruto-skills).

## Codex installation

Add `https://github.com/eruto-skills/marketplace` in Codex's plugin marketplace UI,
then install the plugin you need. Each plugin includes a portable `plugin.json`
and a complete skill under `skills/<name>/SKILL.md`.

For standalone installation into `~/.agents/skills/`, follow the individual plugin README.
Installing a plugin does not install external programs such as Chrome, Python, or Marp.
The instructions select the tools available in the current host.

## Claude Code installation

```text
/plugin marketplace add eruto-skills/marketplace
/plugin install research-note@eruto-skills
```

Replace `research-note` with any plugin name below.

## Plugins

|Plugin|Description|
|-|-|
|[research-note](https://github.com/eruto-skills/research-note)|Research any topic from web, YouTube transcripts, PDFs, X/Twitter posts, or GitHub repos, then generate a footnoted Markdown note with an optional Mermaid mindmap. Includes source-quality tiers and headless-Chrome fetching for bot-protected pages.|
|[research-vault](https://github.com/eruto-skills/research-vault)|Create and maintain a sourced Markdown research vault with topic indexes, integrity checks, and freshness management.|
|[marp](https://github.com/eruto-skills/marp)|Create, edit, and manage Marp (Markdown) presentation slides with a design-first approach. Five modes (create, edit, theme, convert, read/summarize), a layout pattern library, and a 60-30-10 color system with WCAG contrast verification.|
|[presentation](https://github.com/eruto-skills/presentation)|Plan a presentation end-to-end before implementation. Triages requirements, designs the story arc, generates a slide outline, and runs structure QA — then routes the build to a marp or pptx skill. Includes structure-pattern library, content-strategy reference, QA checklist, and outline template.|
|[slide-visual-reviewer](https://github.com/eruto-skills/slide-visual-reviewer)|Verify slide visual quality from PDF/PNG output. Detects text overflow, element overlap, margin issues, and other layout problems via visual inspection of PNG images. Designed as a sub-skill invoked from marp/pptx QA workflows, but also usable standalone.|
|[nanj-thread](https://github.com/eruto-skills/nanj-thread)|Generate a Japanese anonymous-forum (なんJ / 2ch / 5ch) style thread where fictitious commenters observe and riff on the user, a project, or a given topic. For creative-writing and parody use.|
|[analyze-video](https://github.com/eruto-skills/analyze-video)|Analyze a YouTube reference video's structure and rhetorical techniques. Fetches subtitles via yt-dlp, then extracts macro/micro structure, hooks, pacing, hedging, persuasion patterns, retention tactics, and memorable phrases as a Markdown report.|
|[review-content](https://github.com/eruto-skills/review-content)|Review the content quality of a video, presentation, or long-form narration on 18 axes (structure / content / delivery / persuasion). Outputs an A/B/C/D scorecard with concrete improvement actions. Optional source-of-truth comparison and rewrite suggestions.|
|[autopilot](https://github.com/eruto-skills/autopilot)|Plan and run long tasks in Codex or Claude Code with observable completion criteria, lessons, and iteration limits.|
|[design-deai](https://github.com/eruto-skills/design-deai)|Detect AI slop patterns (purple gradients, Inter font fixation, rounded-2xl overuse, glassmorphism, missing Empty/Error states, absent design tokens) in UI source code via static analysis, then generate a DESIGN.md to prevent recurring AI-generated anti-patterns.|
|[design-brief](https://github.com/eruto-skills/design-brief)|Define visual design direction for a Remotion presentation. Reads the content outline, proposes 2-3 design concepts (color palette, typography, animation language, mood), then generates a theme TypeScript file.|
|[ui-visual-reviewer](https://github.com/eruto-skills/ui-visual-reviewer)|Audit a web app's rendered UI colors using getComputedStyle. Calculates WCAG contrast ratios and validates against design tokens — captures opacity-stacked and CSS-variable-resolved colors that screenshot review misses.|
|[fetch-web](https://github.com/eruto-skills/fetch-web)|Fetch web page content as Markdown using a tiered strategy: r.jina.ai (primary), headless Chrome with Puppeteer (fallback), direct curl (last resort). Shared utility referenced by other skills.|
|[fetch-asset](https://github.com/eruto-skills/fetch-asset)|Download media files (MP3/MP4/PNG/SVG/etc.) from the web using the right tool for each source: yt-dlp for video/audio, gallery-dl for image galleries, a Pixabay CDN extractor script, aria2 for parallel downloads, and curl for direct links.|
|[cook-idea](https://github.com/eruto-skills/cook-idea)|Generate original cooking ideas from a user-provided culinary laws vault, cross-check conditions and evidence, and write idea notes.|
|[meal-planner](https://github.com/eruto-skills/meal-planner)|Plan balanced meals and course menus, with recipe templates, food science, scaling, and safety references.|
|[mod-idea-dig](https://github.com/eruto-skills/mod-idea-dig)|Discover Minecraft mod and datapack candidates, remove duplicates, classify them against project criteria, and draft candidates for human selection.|
|[screenshot](https://github.com/eruto-skills/screenshot)|Open a URL in Chromium and save the rendered screen as a PNG, with viewport, dark mode, and wait options.|
|[steam-review](https://github.com/eruto-skills/steam-review)|Write a Steam store review in Steam's BBCode format, with genre-based structure patterns, tone guides, and a QA checklist. Saves each review as a Markdown file with frontmatter (title, store URL, genre, playtime, rating).|

## Release maintenance

Each skill keeps its standalone source at the root and generates its plugin layout
with `node scripts/package-plugin.mjs`. CI runs `--check` to detect stale copies.
Publish the plugin changes before updating this catalog's matching version numbers.

## License

The marketplace is MIT licensed. Each plugin includes its own LICENSE.
