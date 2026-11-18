---
date: '2026-11-18T16:50:00+05:30'
title: 'How to connect GitHub.IO domain with Discord Connections'
draft: false
tags: ["discord", "github"]
image: "https://img.youtube.com/vi/u4ZtHAZ4iZA/0.jpg"
---

Don't have a professional domain? Hosting your site on GitHub Pages? Want to connect your domain to Discord? It might seem complicated, but in reality, it’s not difficult at all.

If you host your personal site or portfolio on **GitHub Pages** (`username.github.io`) instead of a paid custom domain, you can still verify and display it on your Discord profile under **Connections**.

# How to Add a github.io Domain to Discord Connections

## Prerequisites (I know you already have them)

* A **Discord** account (via the desktop app or browser).
* An active **GitHub Pages** site hosted at `yourusername.github.io` (otherwise, visitors clicking the link on your profile will hit a `404` page).

---

## Step 1: Start Domain Verification in Discord

1. Log in to [**Discord**](https://discord.com/channels/@me) and navigate to **User Settings** (or open your profile settings) and go to **Connections**.
2. Click **Add Connection** (or view more options) and select the **Domain** or <img height="25" alt="300327181-ed6ec647-f3d1-432e-bf00-94afdc4afdff" src="https://github.com/user-attachments/assets/b8e0ebe4-f078-4fc4-8a0c-a8678901ab6e" />
 option.
3. Enter your GitHub Pages domain (for example, `yourusername.github.io`—without `https://`) and click **Next**.
4. Choose **Verify using HTTPS**.
5. Copy **only the verification content string** provided by Discord (something like `dh=de494bdb467d8b48177dbd829c5d86ce15c5030b`). Keep this tab open.

---

## Step 2: Create a `.well-known` Repository on GitHub

Because Discord checks `https://yourusername.github.io/.well-known/discord` to confirm domain ownership, you can serve that exact path using a dedicated GitHub repository:

1. Log in to [**GitHub**](https://github.com), click the **`+`** icon in the top-right corner, and select [**New repository**](https://github.com/new).
2. Set the **Repository name** to: `.well-known`
   *(Make sure it is all lowercase and includes the leading dot and hyphen.)*
3. Keep the repository **Public**, and leave **Add a README file**, **.gitignore**, and **License** unchecked (because these are unnecessary).
4. Click **Create repository**.

---

## Step 3: Add the `discord` Verification File

1. On your new `.well-known` repository page, click **creating a new file**.
2. Name the file: `discord`
   *(Do not add `.txt` or any other file extension.)*
3. Paste the verification string you copied from Discord into the file editor (something like `dh=de494bdb467d8b48177dbd829c5d86ce15c5030b`). 
4. Click **Commit changes...** and confirm the commit.

---

## Step 4: Enable GitHub Pages for the Repository

1. Inside the `.well-known` repository, go to **Settings** > **Pages** (in the left sidebar).
2. Under **Build and deployment** > **Branch**, change `None` to **`main`** (leaving the folder as `/ (root)`) and click **Save**.
3. Wait a minute and refresh the page until GitHub confirms that your site is live. This publishes your verification file at `https://yourusername.github.io/.well-known/discord`.

---

## Step 5: Complete Verification & Clean Up

1. Switch back to **Discord** and click **Verify**. Your `github.io` domain will now appear on your profile!
2. *(Optional Cleanup)* Once verified, you can go back to your `.well-known` repository's **Settings** and **delete the repository**. Discord no longer requires the file to stay live unless you change your GitHub username or re-verify the domain later.

---

# Conclusion

This information is valid as of today until [Discord](https://discord.com) makes certain changes. If any information provided in this article becomes outdated, I highly recommend contacting me about it. Please reach out by Email or Discord—links are available in the "About" section of my website.

---

# Credits

A huge thanks to [**Priyansh Prajapat**](https://priyazsh.me) for the [original tutorial](https://github.com/priyazsh/.well-known)!
