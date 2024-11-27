# 🌐 Deploying a Portfolio on Vercel 🚀

This guide will walk you through deploying your portfolio using [Vercel](https://vercel.com), GitHub, and a custom domain. Follow these steps to get your project live quickly and professionally!

---

## 📋 Prerequisites

1. **Portfolio Code**: Your portfolio project, ready to deploy.
2. **GitHub Account**: [Sign up here](https://github.com/signup?source=login) if you don’t already have one.
3. **Vercel Account**: [Sign up here](https://vercel.com/signup).
4. **Domain Name**: A domain purchased from a provider like [OVH](https://www.ovh.com), [Namecheap](https://www.namecheap.com), or others.

---

## ✨ Step 1: Create and Push Your Code to GitHub

1. **Create a GitHub repository via the UI**:
    - Log in to [GitHub](https://github.com).
    - Click the **+** button in the top-right corner and select **New Repository**.
    - Fill in the necessary details for your project, such as the repository name, an optional description, and whether the repository should be public or private.
    - Click **Create Repository** to finalize.

   ➡️ **Your repository is now ready to use.**

2. **Clone the repository locally**:
    - On your repository's GitHub page, click the **Code** button to copy the clone URL.
    - Clone the repository to your computer using Git or another version control tool.

3. **Add your code and push it to GitHub**:
    - Place your portfolio files into the cloned repository folder on your computer.
    - Once your files are ready, add them to the local repository, commit the changes, and push them to GitHub.

   ➡️ **Your code is now live and accessible from your GitHub repository!**

---

## ✨ Step 2: Deploy to Vercel

1. Log in to your Vercel account.
2. **Create a new project**:
    - Go to the **Overview** section.
    - Click **Import Project**.  
      ![Import Project](https://vercel.com/_next/image?url=%2Fimages%2Fdocs%2Fimport-github-repo.webp&w=1080&q=75)
    - Select the GitHub repository you just created.

3. **Automatic Configuration**:
    - Vercel will automatically detect popular frameworks (e.g., React, Next.js).
    - Click **Deploy** and wait a few seconds.

4. 🌟 Your portfolio is now live at `https://<your-project>.vercel.app`!

---

## ✨ Step 3: Add a Custom Domain

### 1. Purchase a Domain (if you haven’t already)
Popular providers include:
- [OVH](https://www.ovh.com)
- [Namecheap](https://www.namecheap.com)
- [Google Domains](https://domains.google/)

### 2. Add the Domain to Vercel
1. In Vercel, go to **Settings > Domains**.
2. Add your custom domain.  
   ![Add Domain](https://vercel.com/_next/image?url=%2Fimages%2Fdocs%2Fadd-domain.webp&w=1080&q=75)

### 3. Configure DNS Settings
1. Log in to your domain provider's DNS manager.
2. Add the following records:
    - **CNAME**:
        - Name: `www`
        - Target: `<your-project>.vercel.app`
    - **A Record** (optional if recommended by Vercel):
        - Target: The IP address provided by Vercel.

### 4. Verify and Propagate
- Wait a few minutes for DNS propagation.
- Your portfolio should now be accessible at `https://your-domain.com`.

---

## 🔧 Customization Tips

- **SEO**: Add `meta` tags for better search engine optimization.
- **SSL Certificate**: Vercel automatically provides a free SSL certificate.
- **Performance**: Use Vercel's built-in tools to monitor your site's speed and performance.

---

## 📚 Useful Resources

- [GitHub Documentation](https://docs.github.com)
- [Vercel Documentation](https://vercel.com/docs)
- [OVH DNS Guide](https://docs.ovh.com/en/domains/modify-dns/)

---

## ✉️ Questions?


**Happy Deploying!** 🎉

--- 