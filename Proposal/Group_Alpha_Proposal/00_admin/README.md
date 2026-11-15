# Group Alpha Proposal Repository

This repository contains the Group Alpha proposal split into section files so five students can work and review independently. It preserves the proposal content while organising chapters, references, ownership and diagrams for Git-based collaboration.

## Folder map
- `00_admin/` - title page, team ownership, confirmation tracker and repository guidance.
- `01_chapter_one/` - Chapter One sections.
- `02_chapter_two/` - Chapter Two literature review sections.
- `03_chapter_three/` - Chapter Three methodology and the mapped work plan, budget and risk sections.
- `03b_chapter_four/` - Chapter Four preliminary system requirements and design.
- `04_references/` - chapter-specific APA references and source verification table.
- `05_diagrams/` - diagram list and suggested diagram files.

## Working rules
- Edit only files you own, as listed in `roles_and_ownership.md`.
- To propose a change to someone else's file, leave a comment line at the top instead.
- Preserve proposal wording and citations; do not resolve factual questions without evidence.

## Git workflow
1. Pull from `main` before you start.
2. Use one branch per member named `member/section` (for example, `fred/1.1`).
3. Open a pull request and have the assigned reviewer approve it before merging to `main`.
4. Resolve [CONFIRM] tags in `things_to_confirm.md` when you answer them.

## Assemble the final document
1. Strip the YAML front matter from section files.
2. Concatenate sections in natural numeric order (`ls -v` or `sort -V`), restoring these chapter headings: `CHAPTER ONE: INTRODUCTION`; `CHAPTER TWO: LITERATURE REVIEW`; `CHAPTER THREE: METHODOLOGY`; `CHAPTER FOUR: PRELIMINARY SYSTEM REQUIREMENTS AND DESIGN`.
3. Use the order: `title_page.md`, Chapter One, Chapter Two, Chapter Three (including 3.13-3.15), Chapter Four, then references.
4. Merge the three reference files into one alphabetical APA list, removing duplicate entries.

**Deadline:** The proposal is due 4 December 2026.
