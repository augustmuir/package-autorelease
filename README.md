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

1. In your package folder if not already initialize npm `npm init -y`, create/add a Github repo, and name your package `@YOUR_GITHUB_USERNAME/YOUR_GTIHUB_REPO_NAME`.
```
npm init -y
```

```
// package.json
{
  "name": "@username/reponame", // ex: "@augustmuir/package-autorelease",
  ...
}
```
2. If not already authorized with Github & npm:
  - Generate a Github Personal Access with `write:packages` permission [here](https://github.com/settings/tokens).
  - Authenticate your Github account: `npm login --scope=@YOUR_GITHUB_USERNAME --registry=https://npm.pkg.github.com`.
3. Add `standard-version`
```
npm install -D standard-version@latest
```
4. Add the following script to your `package.json`:
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
