# Put Purrlog online (no logins)

This version keeps its data in a free Firebase database instead of Claude. Anyone
who opens the link can see and log for Oreo and Louis. They don't need an
account, a password or an invite. Plan on about 15 minutes.

You need two files from this folder: `index.html` and `firestore.rules`.

## 1. Create the database (Firebase, free)

1. Go to https://console.firebase.google.com and sign in with a Google account.
2. Click **Create a project**, name it `purrlog`, and turn **Google Analytics off**.
3. In the left menu, open **Build → Firestore Database** and click **Create database**.
   - Pick a location near you (for example `nam5 (United States)`).
   - Choose **Start in production mode** and click **Create**.
4. Open the **Rules** tab, delete everything there, and paste in the whole
   `firestore.rules` file. Click **Publish**.

## 2. Connect the app to the database

1. Click the gear next to **Project Overview** and choose **Project settings**.
2. Under **Your apps**, click the **</>** (Web) icon. Name it `purrlog`, leave
   "Firebase Hosting" unchecked, and click **Register app**.
3. Firebase shows a `firebaseConfig` block. Copy the six values
   (`apiKey`, `authDomain`, `projectId`, `storageBucket`, `messagingSenderId`, `appId`).
4. Open `index.html` in a text editor and find `STEP 1` near the bottom.
   Paste each value between its quotes and save. (You can also paste the config
   to Claude and have it filled in for you. These values aren't secret: they
   end up in every visitor's browser anyway.)

## 3. Put it on the web (Netlify, free)

1. Put `index.html` in a folder by itself.
2. Go to https://app.netlify.com/drop, sign up (free), and drag that folder onto the page.
3. Netlify gives you a link like `https://something.netlify.app`. Under
   **Site configuration → Change site name** you can rename it, for example `oreo-and-louis`.
4. Text that link to Mom, Dad and Frank. Each phone picks its name the first time.
   On iPhone: Share → **Add to Home Screen**. On Android: ⋮ → **Add to Home screen**.

To update the app later, drag the new folder onto the site's **Deploys** page.

## 4. Bring over anything already logged in the Claude version (optional)

1. In the Claude version: **Settings → Download backup**.
2. In the new site: **Settings → Restore from backup** and pick that file.

## Good to know

- **Anyone with the link can edit or delete entries.** That's the trade-off for
  having no logins. Only share the link with family, and use **Download backup**
  now and then. The rules stop cats from being deleted and only accept
  Purrlog-shaped entries, but they can't tell family from strangers.
- **Free limits:** Firebase's free plan allows 50,000 reads and 20,000 writes a
  day. That's plenty for a family. If you ever hit the limit, the app shows a
  message and works again the next day. Nothing is charged unless you add billing.
- **Speed:** the app loads the last 180 days plus every weigh-in. CSV exports and
  backups always include the full history.
