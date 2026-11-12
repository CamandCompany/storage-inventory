# Storage Unit Inventory (GitHub + Supabase version)

Static page on GitHub Pages. Data and photos live in a free Supabase project.
Your original Claude-hosted version is unaffected.

## 1. Supabase (mostly done for you)
Already done: project `storage-inventory` created, database table, photo storage and sign-in rules applied, and the project URL and key filled into `index.html`.
Still to do in the Supabase dashboard (these settings are not available to Claude):
1. **Authentication -> Users -> Add user**: add your own email (tick "Auto confirm user"). Add anyone else who should have access.
2. **Authentication -> Sign In / Providers**: turn OFF "Allow new users to sign up" so only invited people can get in.

## 2. GitHub
1. Create a new repository (public is fine for Pages on a free account).
2. Upload `index.html` to the repository root. Then **Add file -> Create new file**, name it `.github/workflows/keepalive.yml`, and paste in the contents of `keepalive.yml`.
3. **Settings -> Pages**: Source = "Deploy from a branch", Branch = `main`, folder = `/ (root)`. Your site address appears there after a minute or two.
4. **Settings -> Secrets and variables -> Actions -> New repository secret**: add `SUPABASE_URL` = `https://slvwbngmnzqaiyrofqpj.supabase.co` and `SUPABASE_KEY` = the anon key that is in `index.html`.
5. **Actions tab -> Keep Supabase awake -> Run workflow** once to confirm it succeeds.

## 3. Tell Supabase your site address
**Authentication -> URL Configuration**: set **Site URL** to your GitHub Pages address (for example `https://yourname.github.io/yourrepo/`) and add it under **Redirect URLs** too.

## 4. First use
Open your site, enter your invited email, open the emailed link on the same device, and you are in. The phone stays signed in afterwards.
Print QR labels only AFTER this address is final, because the codes contain it.

## Notes
- Other devices see changes after a reload or when you switch back to the tab.
- Photo links are public to anyone who has the exact link; only signed-in users can add or delete photos.
- GitHub can switch off scheduled jobs in a repo with no activity for about 60 days. Check the Actions tab now and then, and keep using Export CSV as a backup.
- The Supabase free plan pauses a project after 7 days with no activity. If it ever pauses, restore it from the Supabase dashboard.
