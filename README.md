[README.md](https://github.com/user-attachments/files/27371273/README.md)
# Announcement Board

Live announcement display with a rotating message strip, clock, and embedded YouTube playlist.

## Deploy to GitHub Pages

1. Create a new repo (suggestion: pick a non-obvious name like `rma-board-x7k2` rather than `announcement-board` — the URL is public, so an unguessable slug is your only obscurity).
2. Upload `index.html` to the root.
3. Settings → Pages → Source: **Deploy from a branch** → Branch: **main**, Folder: **/ (root)** → Save.
4. Wait ~1 minute. URL will be `https://<your-username>.github.io/<repo-name>/`.
5. Open that URL on the display device. Done.

## Editing announcements

Open `index.html`, find the `CONFIG` block near the top of the `<script>` tag (around line 320). Edit the `announcements` array, commit, push. GitHub Pages redeploys in ~30 seconds.

## Changing the playlist

Find the `<iframe id="yt-iframe">` in the HTML. Replace **only** the playlist ID after `list=`. Keep the path as `/embed/videoseries` — that's the only YouTube endpoint allowed in iframes. The big comment block above the iframe spells out which params do what if you want to tweak behavior.

## Privacy note

GitHub Pages URLs aren't indexed by Google unless someone links to them, but anyone with the URL can read it. The current board has names + PTO info on it, so don't post the URL in public Slack channels, Twitter, etc. If you ever need it actually-private, that requires a paid GitHub plan (Pages from a private repo).
