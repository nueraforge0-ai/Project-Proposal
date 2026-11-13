# Nkumba University Lost and Found Proposal

## Project focus

This project is focused on the design, implementation, and evaluation of a web-based Lost and Found Property Management System with AI-assisted location analytics for the School of Computing and Informatics (SCI), Nkumba University.

## Decisions recorded in the proposal

- Anyone may browse and search approved found-item listings by category without an account or fee.
- Students create accounts with their student details only when they want to submit a claim. Students cannot post lost-item reports or found-item listings.
- The SCI Assistant Administrator and authorised Security personnel may post found-item listings. Security works around the clock and may post items received outside office hours.
- Security records collection and custody, reviews and approves or rejects claims, and records approved handovers. Where an item is first held at the School office, Security records its collection.
- The Assistant Administrator and authorised system administrators may edit or hide/archive listings with a reason. Hidden or archived records and their audit histories are retained.
- Public listings must not expose student details, private claim evidence, or exact storage references. University-approved identity verification, ownership evidence, retention rules, and operating procedures remain to be confirmed.
- The geographic scope is SCI. Campus Security may participate in the workflow, while the system’s records and analysis concern SCI-associated items.
- AI is scoped to aggregate location and status analytics and optional staff-facing explanations/chat. Database queries calculate exact counts and charts; an approved server-side AI API may explain those aggregates. AI does not match items, assess claimants, verify ownership, approve claims, or authorise releases.
- Found locations recorded by staff are kept separate from claimant-reported lost locations. Lost-location analytics are limited to Security-approved claims with a completed handover recorded, and remain labelled as claimant-reported rather than independently verified.
- The proposed stack is a React Progressive Web App, PHP/Laravel backend, and MySQL database. Any AI API is called by the backend; its provider, costs, terms, and data region require University approval. Online actions require a server connection.

## Files

- `Lost_and_Found_Proposal_Working_Copy.docx` — current proposal copy reflecting the decisions above.
- `history/` — original project documents retained as an archive.

The proposal is a working research document. Items such as exact University procedures, identity verification, claim evidence rules, retention, AI provider, sample size, schedule, and budget still require confirmation with the University and supervisor.


## Contributing

Use the following workflow when contributing with Git. Replace `<repository-url>` with the repository URL shared by the project team.

### 1. Clone the repository

```bash
git clone <repository-url>
cd Project-Proposal
```

If you already have a local copy, open its project folder instead of cloning it again.

### 2. Pull before starting or editing

Everyone should sync with the shared branch before making changes, so their work starts from the latest version:

```bash
git switch master
git pull origin master
```

If your team uses a different shared branch, substitute its name for `master`. If Git reports local uncommitted changes or a conflict, save or commit your work and resolve the issue before continuing; do not overwrite another contributor?s changes.

### 3. Make and review your changes

Edit the working proposal, README, or other agreed project files. Keep archived originals in `history/` unchanged unless the team explicitly agrees otherwise. Before committing, review what changed:

```bash
git status
git diff
```

### 4. Commit your contribution

Stage only the files you intend to contribute, then commit with a clear message:

```bash
git add README.md Lost_and_Found_Proposal_Working_Copy.docx
git commit -m "Describe your contribution"
```

Adjust the staged filenames to match your changes. Do not include private credentials, API keys, or personal data in commits.

### 5. Pull again, then push

Before pushing, sync once more in case another contributor has updated the shared branch:

```bash
git pull --rebase origin master
git push origin master
```

If Git reports conflicts, resolve and review them before pushing. Do not force-push to the shared branch; coordinate with the team if the push is rejected or the branch has changed.
