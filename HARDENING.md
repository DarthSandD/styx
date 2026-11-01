# Hardening, Styx repo, checked 2026-11-02

This repo was audited before publish, and again after publish,
because it is public at https://github.com/DarthSandD/styx

## What is in the repo, remote file list

Markdown, one SVG logo, one WebP hero image, and .gitignore only:
.gitignore, CLAUDE-global-rule.md, INDEX.md, README.md, ROUTING.md,
SECURITY.md, USAGE.md, darren-labs-router-SKILL.md,
darren-labs-verify-SKILL.md, logo.svg, styx-auto-SKILL.md,
styx-combine-SKILL.md, styx-hero.webp, styx-manual-pick-SKILL.md

No scripts, no installers, no hooks, no JSON with URLs, no
binary executables, no .env, no credentials file.

## Scans run, with results

- Secret patterns, including ghp_, gho_, sk-, private key
  headers, password equals, api key equals, Bearer tokens:
  no matches in repo files.
- Internal hosts and IPs, including tailnet, Tailscale, and
  public VM IPs: no matches in repo files.
- Signed URLs, including Facebook CDN and signed parameters:
  no matches. One such file was found in a local draft before
  publish and was deleted before the first commit, so it is
  not in remote history for this repo.
- Installer commands, including curl pipe to shell, wget pipe
  to shell, pip install, npm install, npx: no matches in repo files.
- Personal identifiers in repo files, including phone, address,
  bot id, and personal email: no matches in repo files.

## One finding, in git metadata, not in repo files

The first commit author email is a personal Gmail, because
git config used that email at commit time. That email is in
commit metadata on GitHub, as it is for most GitHub commits,
but it is not in any repo file, and it is not a password or
a token.

Fix going forward: use a GitHub noreply email for future
commits, for example DarthSandD@users.noreply.github.com
Rewriting the first commit to remove that email needs a
force push and a separate approval, because it rewrites
public history. It was not done in this hardening pass.

## Rules that stay

- Skill files only. No installer, hook, or MCP install is
  added without a separate review.
- No secret, key, token, password, signed URL, personal email,
  phone, address, internal host, or IP is added to this repo.
- If a secret is ever found, remove it, rotate it, and do not
  rely on making the repo private alone, because public
  history can already be cloned.
- This repo is public, so treat every file in it as public
  forever, even if visibility is changed later.
