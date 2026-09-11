# New Word Wall

New Word Wall is David DeBonis's Hugo-powered journal of linguistics and writing, as well as a repository for research, field notes, tools, and experiments.

## Local development

```sh
hugo server --buildDrafts
```

Open the local URL Hugo prints, usually `http://localhost:1313/`.

## Publishing content

Use the archetype that matches the work:

Use the project wrapper so every entry is created as a Hugo page bundle:

```sh
./scripts/new-content journal article-slug
./scripts/new-content writing essay-slug
./scripts/new-content linguistics essay-slug
./scripts/new-content research project-slug
```

Each command creates a folder containing `index.md`, ready for images and other
article-specific assets:

```text
content/journal/article-slug/index.md
```

Each new file starts as a draft. Add a specific description, useful topics, and relevant disciplines or methods, then change `draft: true` to `draft: false` when it is ready to publish.

### Article previews and featured images

Journal pages automatically show a preview made from the first paragraph of the article. To control that text, add a `summary` field to the front matter:

```yaml
summary: "A concise two-sentence preview for the Journal listing."
```

For a featured image, put the image inside the article's page-bundle folder and add:

```yaml
cover:
	image: "featured-image.png"
	alt: "A specific description of what the image shows"
	caption: "Optional caption shown with the image."
	relative: true
```

The same image can appear in the article body with:

```markdown
![A specific description of what the image shows](featured-image.png)
```

Research pages should distinguish observation from interpretation and claim. Include the research question, evidence, method, sources, limitations, and status. Do not present an unverified hypothesis as a finding.

## Site structure

- `content/journal/` contains general essays and field notes; its public listing also includes published pieces from `content/writing/` and `content/linguistics/`.
- `content/writing/` contains essays and other writing-led work.
- `content/linguistics/` contains essays and studies centered on language.
- `content/projects/` contains research projects.
- `content/about/`, `content/tools/`, and `content/contact/` contain site pages.
- `topics/`, `disciplines/`, and `methods/` make related work discoverable.

## Production build

```sh
hugo --minify
```
