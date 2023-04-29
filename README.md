# package-autorelease

This repository is a step-by-step guide to creating a private Github package which automatically handles versioning and releases via a release script. 

## Steps to create a new package

### 1. Create a git repo with an npm package
- Use the command `npm init -y` to create a new npm package.
- The name of the package must be in the format `@YOUR_GITHUB_USERNAME/YOUR_REPO_NAME`, for example: `@augustmuir/my-private-repo`.

### 2. Create a Github Personal Access token
- Create a Github Personal Access token [here](https://github.com/settings/tokens).
- The only permission needed is `write:packages`.

### 3. Authenticate using Github
- Run the command `npm login --scope=@OWNER --registry=https://npm.pkg.github.com`, replacing `@OWNER` with your Github username (for example: `@augustmuir`).
- No npm account/server is needed for authentication.

### 4. Automate releases via a release script
- Install the `standard-version` package with the command `npm install -D standard-version@latest`.
- Add the following script to your `package.json` file:
    ```
    "scripts": {
        "release": "standard-version && git push --follow-tags && npm publish"
    }
    ```

## Usage
- Commit and push to your branch as needed.
- When you want to create a new version, simply run `npm run release` and a new release, along with a changelog, will be generated automatically.
- To use the package in other projects, run the command `npm install @augustmuir/my-private-repo`, replacing `@augustmuir/my-private-repo` with your own Github username/repo name.

For more information, check out this [article](https://adevait.com/software/publish-private-npm-packages-with-github-package-registry) on publishing private npm packages with Github Package Registry.
