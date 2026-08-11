# Setting Up the Content Management System (Decap CMS)

## Project structure
```
index.html              ← the site itself
content/projects.json   ← project data (edited via the CMS)
content/settings.json   ← hero title, email, etc. (edited via the CMS)
admin/index.html        ← content manager entry page
admin/config.yml        ← defines which fields are editable
```

## Setup steps

1. **GitHub** — create a new repo and push all these files into it — not just index.html, the whole folder: content, admin, images.
2. **Netlify** — go to netlify.com, "Add new site" → "Import an existing project" → connect the GitHub repo. Let Netlify deploy it (no build step needed, it's static).
3. **Enable Identity** — in the site's Netlify dashboard: Site configuration → Identity → Enable Identity.
4. **Enable Git Gateway** — still under Identity settings: scroll to Services → Git Gateway → Enable Git Gateway.
5. **Invite yourself as a user** — Identity → Invite users → enter your email. You'll get an invite email — click the link, it takes you to the site and asks you to set a password.
6. **Log in** — go to `yoursite.netlify.app/admin` and sign in with your email and password.
7. From here it's a plain form: edit projects, main text, upload images. Every save creates a commit on GitHub, and Netlify automatically rebuilds the site within a minute or two.

## Notes
- **Video** field expects an embedded Vimeo player link (`https://player.vimeo.com/video/XXXXXXX`), not a file upload — this keeps the site lightweight.
- If a project's image and video are both left empty, a temporary placeholder graphic is shown (as in the demo).
- Custom domain: in Netlify you can connect your own domain under Domain settings.
