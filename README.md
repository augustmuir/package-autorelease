<h1 align="center">Package-AutoRelease</h1>
<p align="center">
  <b>The Ultimate Guide to Effortlessly Automate Versioning and Releases for Your Private (or public) Github Packages</b>
  <br>
</p>

Package-AutoRelease is a tool designed to help you easily automate the versioning and release process of your Github packages (private or public).

## 🚀 Features

- Easy-to-follow, step-by-step instructions to help you create your own private Github package for your code.
- Automatic versioning and releases with a single command thanks to `standard-version`.
- Seamless authentication via Github, with no need for an npm account/server.
- Commitizen-friendly commits and automatically generated changelogs.

## 🎉 Getting Started

Getting started with Package-AutoRelease is a breeze. Follow these simple steps to automate your versioning and releasing:

1. Create a git repo with an npm package (`npm init -y`).
    - The name of the package **must** be `@YOUR_GITHUB_USERNAME/YOUR_REPO_NAME`, e.g. `@augustmuir/my-private-repo`.
2. Create a Github Personal Access token [here](https://github.com/settings/tokens).
    - Only permission needed is `write:packages`.
3. Authenticate using Github (no npm account/server is needed).
    - With `@OWNER` being your Github username (e.g. `@augustmuir`), run `npm login --scope=@OWNER --registry=https://npm.pkg.github.com`.
4. Automate releases via a release script:
    - Install `standard-version` with `npm install -D standard-version@latest`.
    - Add the following script to your `package.json`:
        ```
        "scripts": {
            "release": "standard-version && git push --follow-tags && npm publish"
        }
        ```

## 💻 Usage

Using Package-AutoRelease is as simple as:

- Commit and push to your branch as needed.
- When you're ready to create a new release, simply run `npm run release`, and a new release with a changelog will be generated automatically.
- Use the package in other projects via: `npm install @YOUR_GITHUB_USERNAME/YOUR_REPO_NAME` (replace github username/repo name).