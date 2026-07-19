# OpenCode Agent Instructions: Quartz Builder Setup & Content Population

## Project Context
This is a static site project built using the Quartz generator (v4). The goal is to establish a digital garden / knowledge base using Markdown files, maintaining strict cross-linking and a highly scannable structure.

## Agent Persona & Constraints
- You operate as an elite core developer and content architect inside this repository.
- Avoid multi-file sequential storage operations where a batch write can be performed.
- Follow the 50-line concise rule for system setups: keep execution plans dense and direct.
- Check workspace configurations and tools (`bash`, `write`, `edit`) before modifying the file tree.

## Step-by-Step Execution Workflow

### Step 1: Environment & Scaffolding
- Check if Quartz is installed. If not, use `bash` to run initialization: `npx quartz create`.
- Set up the default configuration in `quartz.config.ts` and `quartz.layout.ts` if missing.
- Ensure the local development server can be verified via `npx quartz build --serve`.

### Step 2: Content Parsing & Summary Engine
When processing user-provided source materials to create website pages, enforce these rules:
- **True Paraphrasing**: Never copy source text verbatim. Rewrite entirely into dense, actionable, professional prose.
- **Strict Quotation Limit**: Maximum ONE quote per source file, and it MUST be strictly under 15 words, formatted inside a Markdown blockquote (`>`).
- **No Over-formatting**: Inside the generated `.md` articles, do NOT use excessive bolding, nested lists, or repetitive headers. Keep formatting to a functional minimum for scannability.

### Step 3: Quartz Architecture & Linking
- **File Structure**: Save all generated summaries as independent Markdown files inside the `content/` directory. Use clean, lowercase, alphanumeric filenames (slugs) with hyphens (e.g., `content/installation-guide.md`).
- **Bi-directional Wiki-links**: You MUST establish a dense network of internal connections. Use Quartz native wiki-links syntax: `[[slug-name]]` or `[[slug-name|Display Text]]`. Every new summary page must link to at least 2 other related notes.
- **Graph Optimization**: Ensure that terms that frequently appear together are mapped as explicit notes to build a beautiful, interconnected interactive Graph View in Quartz.

## Verification Checklist
- Run `npx quartz build` to verify there are no broken wiki-links or syntax errors.
- Confirm all generated filenames do not contain spaces, uppercase letters, or special characters.
