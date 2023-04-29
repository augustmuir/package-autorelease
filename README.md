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
- Automatically create a changelog with relevant commits for each release.

## 🛠️ Setup

Follow these simple steps to set up and start using Package-AutoRelease:

1. Create a git repository with an npm package. You can use the command `npm init -y` to create a new npm package.
    - The name of the package must be in the format `@YOUR_GITHUB_USERNAME/YOUR_REPO_NAME`, for example: `@augustmuir/my-private-repo`.
2. Generate a Github Personal Access Token with `write:packages` permission [here](https://github.com/settings/tokens).
3. Authenticate your Github account with npm by running `npm login --scope=@OWNER --registry=https://npm.pkg.github.com`, where `@OWNER` is your Github username.
4. Install `standard-version` with `npm install -D standard-version@latest`.
5. Add the following script to your `package.json`:
```
"scripts": {
    "release": "standard-version && git push --follow-tags && npm publish"
}
```

## 🚀 Usage

Using Package-AutoRelease is as simple as:

1. Commit your changes to your branch as needed.
2. When you're ready to create a new release, run `npm run release` to generate a new release with a changelog.
3. You can use the package in other projects via `npm install @YOUR_GITHUB_USERNAME/YOUR_REPO_NAME` (replace github username/repo name).

That's it! With these simple steps, you can automate the versioning and releasing of your Github packages with just a few commands.
