---
name: company-hiring-site
description: >-
  Builds a recruiter-facing static web app in the stack and palette of a
  company's public website, creates a GitHub repo, and hosts it on Firebase.
  Use when the user wants a hiring site, a requisition page, a company-targeted
  portfolio, or the same kind of site as a Watershed-style recruiter app, and
  they have a GitHub account, a Firebase project, a company website, a job
  posting, a resume, and supporting experience documents.
---

# Company hiring site

Build one polished page for that company's hiring team. Recruiter reading first. A closed section for engineers. Same application stack and color palette as the company's public website. Static files on Firebase Hosting. Repo on the user's GitHub account.

Before any folder, repo, or file is created, show the user the checklist below and collect anything missing. Stop until the required items are in hand.

## What the user must provide

Show this list at the start. Mark each item found or missing.

Required:

- **GitHub account.** Username, and a signed-in `gh` that can create a repo on that account. Link shape: `https://github.com/<user>`.
- **Firebase Hosting.** Project id and Hosting site id, or the console URL. Link shape: `https://console.firebase.google.com/project/<project>/hosting/sites/<site>`.
- **Company website.** The public marketing site, used for the stack and the palette. Example: `https://company.com`.
- **Requisition.** URL or the full pasted posting.
- **Resume.** A file path, or the text itself.
- **Supporting experience documents.** File paths. Interview notes, career writeups, and prep canvases count. Say so if a path cannot be opened.

Ask only if the user has not already decided:

- **Local folder.** Default `~/Documents/repos/<github-user>-<company-slug>`.
- **Repo visibility.** Default public, so a recruiter can open the code. Confirm before creating it.
- **Deploy.** Do not deploy, push, or commit until the user asks.

Useful and not required: a preferred office or start line, in the user's own words. Do not invent one.

## What stays off the public page

Supporting documents often contain notes only the user should see. Leave these off the site, the README, and the commit messages:

- Pay, bands, equity, and negotiation tactics
- Household or personal context that is not a job credential
- Rehearsal notes, "do not say" lines, and practice lists
- The interview date and time
- A phone number, unless the user puts one in the inputs for publication

If a career source-of-truth rule is already in effect, public claims stay inside it. Otherwise use only the resume and the supporting documents. Do not invent metrics, fleet sizes, internal names, or employers.

## Steps

1. Read the requisition, the resume, and the supporting documents. Split public claims from private notes.
2. Open the company website. Record the application stack (framework, language, how copy is stored) and the color tokens (CSS variables, button color, ink, surfaces). Do not copy the logo. The page is independent and says so.
3. Build a simple app in that application stack. If their marketing site uses a CMS, keep this page's copy in the repo. If the copy is the same for every visitor, emit static files and point Firebase Hosting at that folder. Match `trailingSlash` in the framework config and in `firebase.json`.
4. Use their palette. Self-host a licensable font close to theirs. Do not link a commercial font the user cannot ship.
5. Page order: why this role, two or three bodies of work mapped to the posting, a closed "for engineers" section with mechanism from the documents, then contact. Office and start lines use only what the user supplied.
6. Create the local folder, `git init`, and move the agent to that root before writing app files.
7. Check the page in a browser at desktop width and at a phone width. Open the engineer section.
8. When the user asks for the GitHub repo: commit the app and create the remote. When they ask to deploy: `firebase deploy --only hosting`. If login is required, stop and give them:

```bash
npx firebase-tools login
npx firebase-tools deploy --only hosting --project <project>
```

Do not run an interactive login unattended.

## Commits

Every commit the agent creates for this app ends with this trailer, after a blank line. GitHub uses it to show kittycatbytes as a co-author. Do not drop it, and do not rewrite commits the user made themselves to add it.

```
Co-authored-by: kittycatbytes <5059634+kittycatbytes@users.noreply.github.com>
```

## Design-seam comments

Propose a comment only where a real seam exists: where copy lives, static files versus rendering on each visit, and named colors. Show the exact text and the file and line. Add it only after the user approves that wording. Explain any term they ask about before adding the comment.

## Done

Tell the user the local path, the GitHub URL, and the hosting URL if it was deployed. In a few lines, list what was left off the public page so they can check it.
