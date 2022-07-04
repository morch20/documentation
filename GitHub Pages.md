# Create a project
---

#### Example: React
1. Create React project
    ```npm
    npm init react-app "name"
    ```
    or using npx

    ```npx
    npx create-react-app "name"
    ```
    or any other package manager

<br>

2. Start app and make sure it is running correctly
<br>

# Install Github pages
---

#### Install github pages to react app
```npm
npm install gh-pages --save-dev
```
<br>

#### Edit package.json
1. Make sure under "devDependencies" has "gh-pages" version
<br>

2. Add on first line
    ```json
    "homepage": "http://[github username].github.io/[repository]"
    ```
<br>

3. Add under scripts
    ```json
    "predeploy": "npm run build",
	"deploy": "gh-pages -d build"
    ```
<br>

# Make a repository for the project and connect it to github
---

#### Create repository inside of the project folder

```git
git init
```
<br>

#### Connect to repository to github
```git
git remote add "remote name" "github repository link"
```
<br>

# Build your project
---

#### Work on your project like you would do normally
<br>


# Deployment
---

#### "commit" your work

```git
git add.
git commit -m "comment"
```
<br>

#### build project for github pages
```
npm run deploy
```
<br>

#### push to github
```git
git push -u origin master
```
<br>

#### Host website on github
1. Click on repository settings
2. Find pages and click on it
3. Open the link and your website has been deployed! :smile:

