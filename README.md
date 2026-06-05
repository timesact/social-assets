# timesact/social-assets

Public host for rendered social media images, used as the URL source for
Buffer drafts (Buffer's GraphQL API requires a publicly-fetchable URL for
image attachments; it does not accept raw uploads).

Files land here via the `pipelines/buffer/upload.py` helper in the private
[`timesact/samwell`](https://github.com/timesact/samwell) repo, which:

1. Copies a rendered PNG into `images/`
2. Renames it with a SHA-1 prefix so the URL is effectively unguessable
3. Commits + pushes
4. Returns the `raw.githubusercontent.com` URL to attach to a Buffer post

**This repo intentionally contains only outputs — no logic.** All rendering
and posting code lives in the private repo.

Old images stay forever; storage is free at this volume and the history
serves as a paper trail of what was posted when.
