# revealjs_cv Tutorial: Building Your CV Website with Reveal.js and GitHub Pages


Video on Bilibili:
- https://www.bilibili.com/video/BV1os421M7WN/


Welcome to the **revealjs_cv** tutorial! This comprehensive guide will walk you through creating a stunning, interactive CV website using [Reveal.js](https://revealjs.com/) and [GitHub Pages](https://pages.github.com/). Whether you're a beginner or looking to enhance your web development skills, this tutorial covers everything you need to know—from setting up your development environment to deploying your site on the cloud.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Getting Started](#getting-started)
   - [1. Cloning the Repository](#1-cloning-the-repository)
   - [2. Understanding the Project Structure](#2-understanding-the-project-structure)
4. [Setting Up Your Development Environment](#setting-up-your-development-environment)
   - [1. Installing VSCode](#1-installing-vscode)
   - [2. Configuring VSCode for Live Preview](#2-configuring-vscode-for-live-preview)
5. [Version Control with Git](#version-control-with-git)
   - [1. Initializing Git](#1-initializing-git)
   - [2. Committing Changes](#2-committing-changes)
   - [3. Pushing to GitHub](#3-pushing-to-github)
6. [Setting Up GitHub Pages](#setting-up-github-pages)
   - [1. Creating a GitHub Repository](#1-creating-a-github-repository)
   - [2. Linking Local Repo to GitHub](#2-linking-local-repo-to-github)
   - [3. Deploying with GitHub Pages](#3-deploying-with-github-pages)
7. [Enhancing Your CV Website](#enhancing-your-cv-website)
   - [1. Customizing Reveal.js](#1-customizing-revealjs)
   - [2. Adding Interactive Elements](#2-adding-interactive-elements)
   - [3. Incorporating Multimedia](#3-incorporating-multimedia)
8. [Advanced Deployment with Docker](#advanced-deployment-with-docker)
   - [1. Dockerizing Your Application](#1-dockerizing-your-application)
   - [2. Deploying to a Cloud VM](#2-deploying-to-a-cloud-vm)
9. [Setting Up SSH for GitHub](#setting-up-ssh-for-github)
   - [1. Generating SSH Keys](#1-generating-ssh-keys)
   - [2. Adding SSH Key to GitHub](#2-adding-ssh-key-to-github)
10. [Best Practices and Tips](#best-practices-and-tips)
11. [Troubleshooting](#troubleshooting)
12. [Conclusion](#conclusion)
13. [Additional Resources](#additional-resources)

---

## Introduction

Creating a personal CV website is an excellent way to showcase your skills, projects, and accomplishments. By leveraging **Reveal.js**, a powerful framework for creating presentations, you can craft an interactive and visually appealing online CV. Hosting your site with **GitHub Pages** ensures it's easily accessible and version-controlled.

This tutorial is designed to guide you through each step of the process, providing detailed instructions and insights to help you build a professional CV website.

---

## Prerequisites

Before diving into the tutorial, ensure you have the following:

- **Basic Knowledge of HTML, CSS, and JavaScript**: Familiarity with web development languages will be beneficial.
- **Git Installed**: Git is essential for version control and interacting with GitHub.
- **GitHub Account**: You'll need an account to host your website via GitHub Pages.
- **VSCode Installed**: [Visual Studio Code](https://code.visualstudio.com/) is recommended for editing your code.
- **Docker (Optional)**: If you plan to deploy using Docker.

---

## Getting Started

### 1. Cloning the Repository

To begin, clone the `revealjs_cv` repository, which contains the template and necessary files for your CV website.


```bash
git clone https://gitee.com/lundechen/revealjs_cv.git
git remote rm origin
git remote add origin git@github.com:<your_github_username>/revealjs_cv.git
```

---

## Setting Up Your Development Environment

### 1. Installing VSCode

[Visual Studio Code](https://code.visualstudio.com/) is a versatile code editor that provides numerous extensions to enhance your development workflow.

- **Download and Install VSCode**:
  - Visit the [VSCode Download Page](https://code.visualstudio.com/download) and select your operating system.
  - Follow the installation instructions specific to your OS.

### 2. Configuring VSCode for Live Preview

To see real-time changes as you edit your HTML, CSS, or JavaScript files, set up live preview functionality.

#### Installing Live Server Extension

1. **Open VSCode**.
2. **Navigate to Extensions**: Click on the Extensions icon in the sidebar or press `Ctrl+Shift+X` (`Cmd+Shift+X` on macOS).
3. **Search for "Live Server"**: Developed by Ritwick Dey.
4. **Install the Extension**.

*Alternatively, use the command line:*

```bash
code --install-extension ritwickdey.LiveServer
```

#### Using Live Server

1. **Open Your Project**: In VSCode, open the `revealjs_cv` folder.
2. **Start Live Server**:
   - Right-click on `index.html` in the Explorer sidebar.
   - Select **"Open with Live Server"**.
3. **View in Browser**: A new browser tab will open, displaying your CV website. Any edits saved in VSCode will automatically refresh in the browser.

---

## Version Control with Git

Version control is crucial for tracking changes and collaborating efficiently. Git, combined with GitHub, offers a robust solution for managing your project.

### 1. Initializing Git

If you haven't already initialized Git in your project, follow these steps.

```bash
git init
```

This command initializes an empty Git repository in your project directory.

*Verify the initialization:*

```bash
git status
```

You should see the untracked files listed.

### 2. Committing Changes

Start tracking your project files and commit your initial setup.

```bash
git add .
git commit -m "Initial commit: Setup revealjs_cv template"
```

- **`git add .`**: Stages all files in the current directory.
- **`git commit -m "..."`**: Commits the staged files with a descriptive message.

### 3. Pushing to GitHub

To host your repository on GitHub and enable GitHub Pages, follow these steps.

#### Creating a GitHub Repository

1. **Log in to GitHub**.
2. **Create a New Repository**:
   - Click the **"+"** icon in the top-right corner and select **"New repository"**.
   - **Repository Name**: `revealjs_cv`
   - **Description**: *Optional* (e.g., "Personal CV website using Reveal.js")
   - **Privacy**: Choose between Public or Private.
   - **Initialize with a README**: *Uncheck* this option since you already have a `README.md`.
3. **Create Repository**: Click **"Create repository"**.

#### Linking Local Repository to GitHub

```bash
git remote add origin git@github.com:<your_github_username>/revealjs_cv.git
```

*Replace `<your_github_username>` with your GitHub username.*           

> **Note:** Using SSH URLs (`git@github.com:...`) enables passwordless authentication once SSH keys are set up.

#### Pushing Your Code

```bash
git push -u origin main
```

- **`-u`**: Sets the upstream branch.
- **`origin`**: The remote repository.
- **`main`**: The branch name.

*If `main` branch doesn't exist yet, you might need to push to `master` or your default branch.*

---

## Setting Up GitHub Pages

GitHub Pages allows you to host your website directly from your GitHub repository. Follow these steps to deploy your CV website.

### 1. Creating a GitHub Repository

If you haven't created a repository yet, refer to [Pushing to GitHub](#3-pushing-to-github). Ensure your repository is either **public** or **private with GitHub Pages enabled**.

### 2. Linking Local Repo to GitHub

Ensure your local repository is linked to the GitHub repository using the SSH remote URL, as shown in [Linking Local Repository to GitHub](#linking-local-repository-to-github).

### 3. Deploying with GitHub Pages

1. **Navigate to Your Repository on GitHub**.
2. **Access Settings**:
   - Click on the **"Settings"** tab.
3. **Select GitHub Pages**:
   - In the left sidebar, click **"Pages"**.
4. **Configure Source**:
   - Under **"Source"**, select the branch you want to deploy (e.g., `main`).
   - Choose the root folder (`/`) if your `index.html` is in the root directory.
5. **Save**:
   - Click **"Save"** to apply the settings.

> **Note:** Deployment may take a few minutes. Once done, GitHub Pages will provide a URL to access your website.

*Example URL:*

```
https://yourusername.github.io/revealjs_cv/
```

*Replace `yourusername` with your GitHub username.*

---

## Enhancing Your CV Website

Elevate your CV website by customizing its appearance and adding interactive features. Here are several ways to make your site stand out.

### 1. Customizing Reveal.js

**Reveal.js** offers extensive customization options to tailor your website's look and feel.

#### Changing Themes

Reveal.js comes with various themes. To change the theme:

1. **Locate Theme Files**: Themes are in the `dist/theme/` directory (e.g., `black.css`, `white.css`).
2. **Modify `index.html`**:
   
   ```html:dist/reveal.css
   <!doctype html>
   <html>
   <head>
       ...
       <link rel="stylesheet" href="dist/theme/black.css">
       ...
   </head>
   ...
   </html>
   ```

   *Change `black.css` to your desired theme, such as `white.css` or any other available theme.*

> **Explore Themes:** Visit the [Reveal.js Themes](https://github.com/hakimel/reveal.js/tree/master/css/theme) repository to view all available themes.

#### Custom CSS

Create a `custom.css` file to override default styles.

```css:css/custom.css
/* Example: Change the background color of slides */
.reveal section {
    background-color: #f0f0f0;
}

/* Example: Customize fonts */
.reveal {
    font-family: 'Arial, sans-serif';
}
```

*Include the custom stylesheet in `index.html`:*

```html:index.html
<head>
    ...
    <link rel="stylesheet" href="css/custom.css">
    ...
</head>
```

#### Modifying Slide Styles

Adjust slide-specific styles using CSS selectors.

```css:css/custom.css
/* Center-align all headings */
.reveal h1, .reveal h2, .reveal h3 {
    text-align: center;
}

/* Add spacing between list items */
.reveal ul li {
    margin-bottom: 10px;
}
```

### 2. Adding Interactive Elements

Enhance user engagement by incorporating interactive components such as transitions, animations, and embedded media.

#### Slide Transitions

Reveal.js supports various slide transition effects.

*Configure transitions in `index.html`:*

```js:index.html
<script>
    Reveal.initialize({
        // ... other configurations
        transition: 'fade', // Choose from 'none', 'slide', 'fade', 'convex', 'concave', 'zoom'
    });
</script>
```

*Example: Using 'zoom' transition.*

```js:index.html
<script>
    Reveal.initialize({
        // ... other configurations
        transition: 'zoom',
    });
</script>
```

#### Embedded Videos

Embed videos from platforms like YouTube or Bilibili to showcase tutorials or project demonstrations.

```markdown:index.html (within a section)
## My Project Video

<iframe src="https://player.bilibili.com/player.html?bvid=BV1os421M7WN" 
        width="800" 
        height="450" 
        frameborder="0" 
        allowfullscreen>
</iframe>
```

#### Interactive Diagrams

Utilize libraries like [Mermaid](https://mermaid-js.github.io/) to create dynamic diagrams.

1. **Include Mermaid Plugin**:

   *Add Mermaid script in `index.html`:*

   ```html:index.html
   <head>
       ...
       <script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
       ...
   </head>
   ```

2. **Initialize Mermaid**:

   ```js:index.html
   <script>
       mermaid.initialize({ startOnLoad: true });
   </script>
   ```

3. **Add Diagrams in Slides**:

   ```markdown:index.html (within a section)
   ## My Workflow

   ```mermaid
   graph LR
       A[Start] --> B{Decision}
       B -->|Yes| C[Option 1]
       B -->|No| D[Option 2]
       C --> E[End]
       D --> E[End]
   ```
   ```

### 3. Incorporating Multimedia

Adding images, audio, and other media can make your CV more engaging.

#### Adding Images

Include profile pictures, project screenshots, and logos.

```markdown:index.html (within a section)
## About Me

![Profile Picture](img/index/china.png)
```

#### Including Audio

Embed audio clips or background music.

```markdown:index.html (within a section)
## My Favorite Podcast

<audio controls>
  <source src="audio/favorite-podcast.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

> **Tip:** Host audio files in the `audio/` directory and reference them accordingly.

#### Using Icons

Leverage icon libraries like Font Awesome for visual enhancements.

```html:index.html
<head>
    ...
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css" integrity="..." crossorigin="anonymous" referrerpolicy="no-referrer" />
    ...
</head>
<body>
    ...
    <i class="fa-brands fa-github"></i>
    ...
</body>
```

> **Reference:** [Font Awesome Icons](https://fontawesome.com/icons)

---

## Advanced Deployment with Docker

For those interested in deploying their CV website on a cloud VM using Docker, follow these advanced steps.

### 1. Dockerizing Your Application

Docker allows you to containerize your application, ensuring consistency across environments.

#### Understanding the `Dockerfile`

A `Dockerfile` contains instructions to build your Docker image.

```dockerfile:Dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html/
```

- **`FROM nginx:latest`**: Uses the latest Nginx image as the base.
- **`COPY . /usr/share/nginx/html/`**: Copies all project files to Nginx's default HTML directory.

#### Building the Docker Image

```bash
docker build -t revealjs_cv .
```

- **`-t revealjs_cv`**: Tags the image with the name `revealjs_cv`.
- **`.`**: Specifies the current directory as the build context.

#### Running the Docker Container

```bash
docker run -d -p 80:80 revealjs_cv
```

- **`-d`**: Runs the container in detached mode.
- **`-p 80:80`**: Maps port 80 of the host to port 80 of the container.

*Your CV website is now accessible at `http://localhost`.*

### 2. Deploying to a Cloud VM

Deploy your Dockerized application to a cloud service provider like [AWS](https://aws.amazon.com/), [Google Cloud](https://cloud.google.com/), or [DigitalOcean](https://www.digitalocean.com/).

#### Steps Overview

1. **Provision a VM Instance**: Choose your preferred cloud provider and create a new virtual machine.
2. **Install Docker**: Ensure Docker is installed on your VM.
3. **Transfer Your Project Files**: Use `scp` or Git to transfer your project to the VM.
4. **Build and Run Docker Container**: Execute the same Docker commands as above on the VM.
5. **Configure Firewall and DNS**: Open necessary ports and (optionally) configure a custom domain.

*Refer to your cloud provider's documentation for detailed instructions.*

---

## Setting Up SSH for GitHub

Establishing SSH authentication allows you to interact with GitHub repositories securely without entering your password repeatedly.

### 1. Generating SSH Keys

Generate a new SSH key pair on your local machine.

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- **`-t ed25519`**: Specifies the SSH key type.
- **`-C "..."`**: Adds a comment/email for identification.

*When prompted:*

- **File Location**: Press `Enter` to accept the default location (`~/.ssh/id_ed25519`).
- **Passphrase**: Enter a secure passphrase or leave blank for no passphrase.

*Example:*

```bash
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
```

#### Viewing Your SSH Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

*Output:*

```plaintext
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... your_email@example.com
```

### 2. Adding SSH Key to GitHub

1. **Copy the SSH Key**:

   ```bash
   pbcopy < ~/.ssh/id_ed25519.pub  # macOS
   xclip -sel clip < ~/.ssh/id_ed25519.pub  # Linux
   clip < ~/.ssh/id_ed25519.pub  # Windows (Git Bash)
   ```

2. **Navigate to GitHub**:
   - Click on your profile picture and select **"Settings"**.

3. **Access SSH and GPG Keys**:
   - In the left sidebar, click **"SSH and GPG keys"**.

4. **Add New SSH Key**:
   - Click **"New SSH key"**.
   - **Title**: Provide a descriptive name (e.g., "My Laptop SSH Key").
   - **Key**: Paste the copied SSH key.
5. **Save**: Click **"Add SSH key"** and confirm with your GitHub password if prompted.

> **Security Tip:** Keep your private SSH key (`id_ed25519`) secure and never share it.

---

## Best Practices and Tips

- **Commit Often**: Regular commits help track progress and make it easier to revert changes if needed.
- **Write Descriptive Commit Messages**: Clear messages improve project documentation and collaboration.
- **Use Branches**: For significant changes or new features, create separate branches to maintain the stability of the main branch.
  
  ```bash
  git checkout -b feature/custom-theme
  ```

- **Backup Your SSH Keys**: Store your SSH keys in a safe location to prevent loss.
- **Regularly Update Dependencies**: Keep Reveal.js and other libraries up to date for security and feature improvements.
- **Optimize Images**: Compress images to reduce load times without compromising quality.
- **Responsive Design**: Ensure your CV website is mobile-friendly for accessibility across devices.
- **Accessibility Compliance**: Adhere to web accessibility standards to make your website usable for all visitors.
  
  ```html:index.html
  <head>
      ...
      <meta name="description" content="Lunde Chen - Assistant Professor in Computer Science.">
      <meta name="keywords" content="CV, Lunde Chen, Computer Science, Shanghai University, Reveal.js">
      ...
  </head>
  ```

---


## Conclusion

Congratulations! You've successfully built and deployed your personal CV website using Reveal.js and GitHub Pages. This platform not only showcases your professional profile but also demonstrates your web development skills. By following this tutorial, you've gained valuable experience in version control, web design, and deployment strategies.
