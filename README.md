# 🚀 revealjs_cv Tutorial: Building Your CV Website with Reveal.js and GitHub Pages

🎥 **Video on Bilibili:**  
- [https://www.bilibili.com/video/BV1os421M7WN/](https://www.bilibili.com/video/BV1os421M7WN/)

Welcome to the **revealjs_cv** tutorial! This comprehensive guide will walk you through creating a stunning, interactive CV website using [Reveal.js](https://revealjs.com/) and [GitHub Pages](https://pages.github.com/). Whether you're a beginner or looking to enhance your web development skills, this tutorial covers everything you need to know—from setting up your development environment to deploying your site on the cloud.

---

## Introduction

Creating a personal CV website is an excellent way to showcase your skills, projects, and accomplishments. By leveraging **Reveal.js**, a powerful framework for creating presentations, you can craft an interactive and visually appealing online CV. Hosting your site with **GitHub Pages** ensures it's easily accessible and version-controlled.

This tutorial is designed to guide you through each step of the process, providing detailed instructions and insights to help you build a professional CV website.

---

## Getting Started

### 1. Creating a GitHub Repository 🛠️

Before cloning the repository, you need to create one on GitHub.

1. **Log in to GitHub**.
2. **Create a New Repository**:
   - Click the **"+"** icon in the top-right corner and select **"New repository"**.
   - **Repository Name**: `yourusername.github.io` *(Replace `yourusername` with your actual GitHub username)*
   - **Privacy**: Choose **Public**.
   - **Initialize with a README**: no.
3. **Create Repository**: Click **"Create repository"**.

### 2. Cloning the Repository 📂

Clone the `revealjs_cv` repository, which contains the template and necessary files for your CV website.

```bash
git clone https://gitee.com/lundechen/revealjs_cv.git
cd revealjs_cv
```

Link your local repository to the GitHub repository you just created:

```bash
git remote remove origin
git remote add origin git@github.com:yourusername/yourusername.github.io.git
```

*Replace `yourusername` with your GitHub username.*

### 3. Installing Live Server Extension 🔌

To preview your website in real-time, install the Live Server extension in VSCode.

1. **Open VSCode**.
2. **Navigate to Extensions**: Click on the Extensions icon in the sidebar or press `Ctrl+Shift+X` (`Cmd+Shift+X` on macOS).
3. **Search for "Live Server" or "Live Preview"**.
4. **Install the Extension**.

*Alternatively, use the command line:*

```bash
code --install-extension ritwickdey.LiveServer
```

#### Using Live Server

- Right-click on `index.html` in the Explorer sidebar.
- Select **"Open with Live Server"**.
- **View in Browser**: A new browser tab will open, displaying your CV website. Any edits saved in VSCode will automatically refresh in the browser.

### 4. Setting Up Docker Compose 🐳

To streamline your development environment, use Docker Compose.

#### Adding `docker-compose.yml`

Create a `docker-compose.yml` file in the root of your project:

````yaml:docker-compose.yml
version: '3'
services:
  my-great-nginx-web-server:
    image: nginx:latest
    ports:
      - '80:80'
    volumes:
      - type: bind
        source: ./
        target: /usr/share/nginx/html/
    restart: always
````

#### Running Docker Compose

Start your Docker container with:

```bash
docker-compose up -d
```

Your CV website is now accessible at `http://localhost`.

---

## Version Control with Git 🐱‍💻

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

### 2. Committing Changes 📝

Start tracking your project files and commit your initial setup.

```bash
git add .
git commit -m "Initial commit: Setup revealjs_cv template"
```

- **`git add .`**: Stages all files in the current directory.
- **`git commit -m "..."`**: Commits the staged files with a descriptive message.

### 3. Pushing to GitHub 🚀

To host your repository on GitHub and enable GitHub Pages, follow these steps.

#### Linking Local Repository to GitHub

```bash
git remote add origin git@github.com:yourusername/yourusername.github.io.git
```

*Replace `yourusername` with your GitHub username.*

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

## Setting Up GitHub Pages 🌐

GitHub Pages allows you to host your website directly from your GitHub repository. Follow these steps to deploy your CV website.

### 1. Configuring GitHub Pages

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
https://yourusername.github.io/
```

*Replace `yourusername` with your GitHub username.*

---

## Advanced Deployment with Docker Compose 🐳

For those interested in deploying their CV website on a cloud VM using Docker Compose, follow these advanced steps.

### 1. Dockerizing Your Application

Docker allows you to containerize your application, ensuring consistency across environments.

#### Using `docker-compose.yml`

Ensure your `docker-compose.yml` is set up as shown:

````yaml:docker-compose.yml
version: '3'
services:
  my-great-nginx-web-server:
    image: nginx:latest
    ports:
      - '80:80'
    volumes:
      - type: bind
        source: ./
        target: /usr/share/nginx/html/
    restart: always
````

#### Building and Running with Docker Compose

```bash
docker-compose up -d
```

- **`-d`**: Runs the containers in detached mode.

*Your CV website is now accessible at `http://localhost`.*

### 2. Deploying to a Cloud VM ☁️

Deploy your Dockerized application to a cloud service provider like [AWS](https://aws.amazon.com/), [Google Cloud](https://cloud.google.com/), or [DigitalOcean](https://www.digitalocean.com/).

#### Steps Overview

1. **Provision a VM Instance**: Choose your preferred cloud provider and create a new virtual machine.
2. **Install Docker and Docker Compose**: Ensure both are installed on your VM.
3. **Transfer Your Project Files**: Use `scp` or Git to transfer your project to the VM.
4. **Build and Run Docker Containers**: Execute the same Docker Compose commands on the VM.
5. **Configure Firewall and DNS**: Open necessary ports and (optionally) configure a custom domain.

*Refer to your cloud provider's documentation for detailed instructions.*

---

## Best Practices and Tips 💡

- **Commit Often**: Regular commits help track progress and make it easier to revert changes if needed.
- **Write Descriptive Commit Messages**: Clear messages improve project documentation and collaboration.
- **Use Branches**: For significant changes or new features, create separate branches to maintain the stability of the main branch.

  ```bash
  git checkout -b feature/custom-theme
  ```

---

## Conclusion 🎉

Congratulations! You've successfully built and deployed your personal CV website using Reveal.js and GitHub Pages. This platform not only showcases your professional profile but also demonstrates your web development skills. By following this tutorial, you've gained valuable experience in version control, web design, and deployment strategies.

Happy coding! 👨‍💻👩‍💻

