---
date: '2025-02-19T12:37:44+05:00'
draft: false
title: 'Installing and Setting Up Hugo With the Hextra Theme: a Step by Step Guide'
description: "In this guide, I walk you through installing Hugo Extended and setting up the Hextra theme step by step. I cover everything from creating a new Hugo site and configuring the theme using Hugo Modules or Git Submodules to customizing your site and deploying it on various platforms. Follow along to build your modern, responsive static website."
authors:
  - name: TrainedPro
    link: https://github.com/TrainedPro
    image: https://github.com/TrainedPro.png
tags:
  - Hugo
  - Hextra
  - Static Site Generator
  - Markdown
  - Installation
  - Tutorial
---

Welcome to my comprehensive guide on using Hugo with the Hextra theme. In this document, I share a step-by-step process, from installation to deployment, that will help you build a modern, responsive website with ease.

{{< cards >}}
{{< card title="Source Code" subtitle="The source code for the entire project is available on my GitHub." icon="github" link="https://github.com/TrainedPro/trainedpro.github.io">}}
{{< /cards >}}

## 1. Introduction

Welcome to this guide on installing and setting up **Hugo** with the **Hextra** theme. In this post, we'll walk you through everything you need to get started, from installing Hugo to configuring the Hextra theme, so you can build a beautiful, modern website or blog.

### What is Hugo?
Hugo is a fast, modern, and flexible static site generator that transforms your Markdown files into a fully functional website. With its impressive speed and extensive customization options, Hugo is a favorite among developers and content creators alike.

### Introducing Hextra
Hextra is a modern, responsive Hugo theme designed to help you create professional blogs and documentation sites with ease. Key features include:
- **Responsive Design:** Adapts seamlessly to mobile, tablet, and desktop devices.
- **Dark and Light Modes:** Easily toggle between themes to match your content or audience preference.
- **Built-In Full-Text Search:** Powered by FlexSearch, enabling quick and efficient content search.
- **Customizable Layouts and Components:** Simplify your site's configuration and design with a variety of out-of-the-box options.

In this guide, you'll learn how to:
- Set up Hugo on your system.
- Create a new Hugo site.
- Install and configure the Hextra theme using either Hugo Modules or Git Submodules.
- Create your first content pages and preview your site locally.
- Explore deployment options and troubleshooting tips.

Let's get started on building a powerful website with Hugo and Hextra!

## 2. Prerequisites

Before diving into setting up Hugo with the Hextra theme, ensure you have the following tools and knowledge in place.

### Required Software
{{< cards >}}
{{< card title="Hugo (Extended Version)" subtitle="Hugo is a fast static site generator that transforms Markdown files into a full website." icon="hugo" >}}
{{< card title="Git" subtitle="Git is essential for version control and managing theme modules or submodules." icon="github" >}}
{{< card title="Go (Optional)" subtitle="While not mandatory, having Go installed can help with module management." icon="go" >}}
{{< /cards >}}

### Basic Knowledge and Skills
- **Command-Line Usage:** You should be comfortable using terminal commands.
- **Markdown:** Familiarity with Markdown syntax is necessary for creating and editing content.
- **Git Basics:** Understanding Git operations (clone, commit, push) will be beneficial.

{{< details title="Need More Info?" closed="true">}}
For beginners, here are some useful resources:
- [Hugo Documentation](https://gohugo.io/)
- [Git Book](https://git-scm.com/book/en/v2)
- [Markdown Guide](https://www.markdownguide.org/)
{{< /details >}}

## 3. Installing Hugo

In this step, we'll install the **extended version of Hugo**, a requirement for taking full advantage of the Hextra theme.

{{< cards >}}
  {{< card link="https://gohugo.io/getting-started/installing/" title="Official Hugo Installation Guide" icon="external-link" >}}
{{< /cards >}}

> [!IMPORTANT]
> Ensure you download and install the **extended version** of Hugo, which includes SCSS processing and other advanced features needed by Hextra.

{{< tabs items="macOS,Linux,Windows" >}}

{{< tab >}}
{{% steps %}}
### Install Hugo  
Using Homebrew, run:
```bash
brew install hugo
```

### Verify Installation  
Run:
```bash
hugo version
```
You should see the installed Hugo version.
{{% /steps %}}
{{< /tab >}}

{{< tab >}}
{{% steps %}}
### Install Hugo  
Using Snap, run:
```bash
sudo snap install hugo --channel=extended
```

### Verify Installation  
Run:
```bash
hugo version
```
Ensure the correct version is displayed.
{{% /steps %}}
{{< /tab >}}

{{< tab >}}
{{% steps %}}
### Install Hugo  
Using Chocolatey, run:
```powershell
choco install hugo-extended -y
```

### Verify Installation  
Run:
```powershell
hugo version
```
Confirm that Hugo is installed by checking the version output.
{{% /steps %}}
{{< /tab >}}
{{< /tabs >}}

> [!TIP]
> If you prefer not to use a package manager, you can manually download the Hugo Extended binary from the [Hugo Releases page](https://github.com/gohugoio/hugo/releases) and follow the provided installation instructions.

Once Hugo is installed and verified, you're ready to move on to creating your new Hugo site!

## 4. Creating a New Hugo Site

In this step, you'll create a new Hugo site that will serve as the foundation for your project.

> [!NOTE]
> Replace `my-site` with your desired project name.

{{% steps %}}

### Open Your Terminal  
Open your preferred terminal application.

### Create the Site  
Run the following command to create a new Hugo site using YAML as the configuration format:
```bash
hugo new site my-site --format=yaml
```

### Navigate to Your Site Directory  
Change into your new site's directory:
```bash
cd my-site
```
{{% /steps %}}

> [!IMPORTANT]
> This command sets up the basic directory structure for your Hugo site. You'll see folders like `content`, `layouts`, `static`, etc.

Once your site is created, you're ready to install the Hextra theme and move on to configuration.

## 5. Installing the Hextra Theme

> [!TIP]
> The Hugo Modules method is recommended because it automatically handles theme updates and dependencies.

{{< tabs items="Hugo Modules,Git Submodules" >}}

{{< tab >}}
{{% steps %}}
### Initialize the Hugo Module  
> [!NOTE]
> Replace `yourusername/mysite` with your username and desired project name.
Navigate to your site directory and run:
```bash
hugo mod init github.com/yourusername/my-site
```

### Add the Hextra Theme  
Run the following command to add Hextra:
```bash
hugo mod get github.com/imfing/hextra
```

### Configure Your Site  
Open your `hugo.yaml` (or equivalent config file) and add the following to import the theme:
```yaml
module:
  imports:
    - path: github.com/imfing/hextra
```
{{% /steps %}}
{{< /tab >}}

{{< tab >}}
{{% steps %}}
### Add Hextra as a Submodule  
Run this command in your site directory:
```bash
git submodule add https://github.com/imfing/hextra.git themes/hextra
```

### Update the Configuration File  
In your `hugo.yaml`, set the theme by adding:
```yaml
theme: hextra
```
{{% /steps %}}
{{< /tab >}}
{{< /tabs >}}

Once you've installed Hextra using your preferred method, you're ready to move on to configuring the theme for your site.

## 6. Configuring the Hextra Theme

Once you've installed the Hextra theme, it's time to configure it to suit your site's needs. This is done by editing your configuration file (e.g., `hugo.yaml`) in your site's root directory.

> [!TIP]
> Hextra offers a wide range of configuration options for customizing your site's layout, navigation, and appearance. For more details, refer to the [Hextra Documentation](https://imfing.github.io/hextra/docs/guide/configuration/).

{{% steps %}}

### Open Your Configuration File  
Locate and open the configuration file (for example, `hugo.yaml`) in the root directory of your Hugo site.

### Set Basic Site Parameters  
Define your site's essential details such as the base URL, title, and language:
> [!NOTE]
> Replace `baseURL`, `title` and `languageCode` with your desired values.
```yaml
baseURL: "https://example.com/"
title: "My Hugo Site"
languageCode: "en-us"
```

### Configure Hextra-Specific Settings  
Customize the Hextra theme by adding or updating the following parameters under `params`:
```yaml
params:
  navbar:
    displayTitle: true
    displayLogo: true
    logo:
      path: "images/logo.svg"
      dark: "images/logo-dark.svg"
      link: "/"
      width: 40
      height: 20
  theme:
    default: system  # Options: system, light, dark
    displayToggle: true
```

### Customize Menus and Other Elements  
Set up your navigation menu and other site elements as needed:
```yaml
menu:
  main:
    - name: "Documentation"
      pageRef: "/docs"
      weight: 1
    - name: "Blog"
      pageRef: "/blog"
      weight: 2
```
{{% /steps %}}

> [!IMPORTANT]
> After updating your configuration, restart your Hugo server to apply the changes.

With your Hextra theme now configured, you're ready to start creating content and further customizing your site.

## 7. Creating Your First Content Pages

Now that your Hugo site is set up and the Hextra theme is configured, it's time to start adding content to your site. In this step, you'll create a homepage and a documentation page using Hugo's `new` command.

> [!TIP]
> Use the `hugo new` command to quickly generate content files with the appropriate front matter.

{{% steps %}}

### Create the Homepage  
Run the following command to generate your homepage:
```bash
hugo new content/_index.md
```

### Create the Documentation Page  
Generate a new page for documentation:
```bash
hugo new content/docs/_index.md
```

### Edit Your Content Files  
Open the newly created files in your preferred text editor. Customize the front matter and add your content. For example, your `content/_index.md` might start like this:
```yaml
---
title: "Welcome to My Hugo Site"
date: 2025-01-01T12:00:00Z
draft: true
---
```
Then add your Markdown content below the front matter.
{{% /steps %}}

> [!IMPORTANT]
> **Remember:** Set `draft: false` to publish your content on your live site.

For more details on organizing content, you might find the following resource helpful:
{{< cards >}}
  {{< card link="https://gohugo.io/content-management/organization/" title="Hugo Content Organization" icon="external-link" >}}
{{< /cards >}}

Once you've created and customized your content pages, you're ready to preview your site locally.

## 8. Running the Site Locally

Now that your content is in place, it's time to preview your site locally and see your changes in action.

> [!TIP]
> Use the `hugo server` command with the `--buildDrafts` flag to preview draft content and `--disableFastRender` for more reliable live-reloading.

{{% steps %}}

### Start the Local Server  
Open your terminal in your site's root directory and run:
```bash
hugo server --buildDrafts --disableFastRender
```

### Access Your Site  
Once the server is running, open your browser and navigate to:
```plaintext
http://localhost:1313/
```

### Test Your Changes  
Edit your content files and save them, your site should automatically refresh to reflect your changes.
{{% /steps %}}

> [!IMPORTANT]
> If you encounter any issues, review your terminal output for error messages and ensure your configuration files are correctly set up.

With your site running locally, you can now test and fine-tune your content before moving on to deployment.

## 9. Deployment Options

Once your site is running perfectly on your local machine, it's time to deploy it and share it with the world. Hugo's static output makes deployment quick and simple across many hosting platforms.

> [!TIP]
> GitHub Pages is the recommended deployment option as it is free and the easiest.

{{% steps %}}

### Build Your Site for Production  
Run the following command to generate the production-ready files:
```bash
hugo --gc --minify
```
This command cleans up unused files and minifies your site's assets for optimal performance.

### Deploy Your Site  
I recommend the following deployment methods:
{{< tabs items="GitHub Pages,Netlify,Cloudflare Pages,Vercel,Others" >}}

{{< tab >}}
For GitHub Pages, you can push the contents of your `public/` folder to the `gh-pages` branch, or use GitHub Actions. For example, you might use the workflow below:
{{% details title="GitHub Actions Configuration" closed="true" %}}
Here is a sample workflow
```yaml {filename=".github/workflows/pages.yaml"}
name: Deploy Hugo site to Pages
on:
  push:
    branches: ["main"]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: "pages"
  cancel-in-progress: false
defaults:
  run:
    shell: bash
jobs:
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.138.0
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0
          submodules: recursive
      - name: Setup Go
        uses: actions/setup-go@v5
        with:
          go-version: '1.22'
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v4
      - name: Setup Hugo
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb
      - name: Build with Hugo
        env:
          HUGO_ENVIRONMENT: production
          HUGO_ENV: production
        run: |
          hugo --gc --minify --baseURL "${{ steps.pages.outputs.base_url }}/"
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
{{% /details %}}

By default, this workflow deploys to `https://<USERNAME>.github.io/<REPO>/`. Update the `--baseURL` parameter if you need to deploy to `https://<USERNAME>.github.io/` or your own domain.
{{< /tab >}}

{{< tab >}}
Connect your repository to Netlify. Set the Build command to `hugo --gc --minify` and the Publish directory to `public`. If needed, add the environment variable `HUGO_VERSION` with the value `0.138.0`.
{{< /tab >}}

{{< tab >}}
To use Cloudflare Pages:
1. Push your site source code to a Git repository (e.g. GitHub).
2. In the [Cloudflare dashboard](https://dash.cloudflare.com/), select your account and go to **Workers & Pages** > **Create application** > **Pages** > **Connect to Git**.
3. When setting up builds and deployments, use these configuration values:
   | Configuration     | Value                |
   | ----------------- | -------------------- |
   | Production branch | `main`               |
   | Build command     | `hugo --gc --minify` |
   | Build directory   | `public`             |
For more details, check the [Deploy a Hugo site guide](https://developers.cloudflare.com/pages/framework-guides/deploy-a-hugo-site/#deploy-with-cloudflare-pages).
{{< /tab >}}

{{< tab >}}
Import your Hugo project into Vercel via the [Vercel Dashboard](https://vercel.com/dashboard). In your project settings, select Hugo as the Framework Preset and override the commands as follows:
1. **Build Command:** `hugo --gc --minify`
2. **Install Command:** `yum install golang`
![Vercel Deployment Configuration](https://github.com/imfing/hextra/assets/5097752/887d949b-8d05-413f-a2b4-7ab92192d0b3)
{{< /tab >}}

{{< tab >}}
You can also deploy on Firebase or another static hosting provider by using their specific deployment instructions.
{{< /tab >}}

{{< /tabs >}}
{{% /steps %}}

> [!IMPORTANT]
> **Before deploying:** Ensure that all content is finalised and that your site works flawlessly on your local server.

### Additional Resources
{{< cards >}}
  {{< card link="https://www.netlify.com/" title="Netlify" icon="external-link" >}}
  {{< card link="https://pages.github.com/" title="GitHub Pages" icon="external-link" >}}
  {{< card link="https://vercel.com/" title="Vercel" icon="external-link" >}}
{{< /cards >}}

Once deployed, your site will be live at your configured domain, and you can share it with the world. Enjoy your new Hugo-powered website!
  
## 10. Troubleshooting & FAQs

Sometimes things may not work as expected. In this step, we'll cover some common issues and provide tips for resolving them.

> [!IMPORTANT]
> Always review your terminal output for error messages. Many issues can be quickly resolved by checking the logs.

{{% steps %}}

### Check Your Configuration  
Ensure that your configuration file (e.g., `hugo.yaml`) is correctly formatted and contains all necessary parameters.
Tip: Use an online YAML validator if you're unsure.

### Review Terminal Logs  
When running `hugo server` or building your site, check your terminal for error messages or warnings that may indicate misconfigurations or missing files.

### Verify Theme Installation  
Confirm that Hextra is correctly installed:
- For Hugo Modules: Check your `hugo.mod` file and the module import in your configuration.
- For Git Submodules: Ensure the `themes/hextra` directory exists and is populated.

### Consult the Documentation  
Refer to the [Hextra Documentation](https://imfing.github.io/hextra/docs/) and the [Hugo Documentation](https://gohugo.io/documentation/) for further guidance on troubleshooting specific issues.
{{% /steps %}}

> [!TIP]
> If a page isn't rendering as expected, double-check the front matter in your Markdown files for correct syntax and required fields.

## 11. Conclusion & Additional Resources

In this final step, we wrap up the guide and provide you with additional resources to help you further customize your site and troubleshoot any issues.

### Conclusion
You've now learned how to:
- Install Hugo Extended.
- Create a new Hugo site.
- Install the Hextra theme using either Hugo Modules or Git Submodules.
- Configure the theme to match your needs.
- Create and manage your content pages.
- Run your site locally for testing.
- Deploy your website.

With these steps, you have a solid foundation for building a beautiful and responsive website using Hugo and Hextra. Enjoy experimenting with advanced customizations and make your site truly your own!

### Additional Resources
{{< cards >}}
  {{< card link="https://gohugo.io/documentation/" title="Hugo Documentation" icon="external-link" >}}
  {{< card link="https://imfing.github.io/hextra/docs/" title="Hextra Theme Documentation" icon="external-link" >}}
  {{< card link="https://github.com/gohugoio/hugo" title="Hugo GitHub Repository" icon="external-link" >}}
{{< /cards >}}

> [!IMPORTANT]
> Keep exploring, stay curious, and don't hesitate to seek help in the Hugo and Hextra communities if you need further assistance.

Thank you for following this guide, and happy coding!