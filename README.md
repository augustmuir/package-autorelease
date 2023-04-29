# package-autorelease
create a private Github package which automatically handles versioning and releases (via a release script)

Steps to create a new package:
1. Create a git repo with a npm package (`npm init -y`):
    - The name of the package **must** be `@YOUR_GITHUB_USERNAME/YOUR_REPO_NAME` ex: `@augustmuir/my-private-repo`. 
2. Create a Github Personal Access token [here](https://github.com/settings/tokens)
    - Only permission needed is `write:packages`
3. Authenticate using Github (no npm account/server is needed):
    - With `@OWNER` being your Github username (ex: `@augustmuir`) `npm login --scope=@OWNER --registry=https://npm.pkg.github.com`
4. Automate releases via a release script: 
    - add `standard-version` npm install -D standard-version@latest`
    - add the following script to your `package.json`:
        ```"scripts": {
            "release": "standard-version && git push --follow-tags && npm publish"
        }```

**Usage**
- commit and push to your branch as needed
- when you want to create a new version simple run `npm run release` and a new release along with a changelog will be generated automatically
- use the package in other projects via: `npm install @augustmuir/my-private-repo` (replace github username/repo name)


More info: https://adevait.com/software/publish-private-npm-packages-with-github-package-registry