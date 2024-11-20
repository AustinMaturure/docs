# Migarting from Docusaurus to Mintlify

`Mintlify` is designed to help developers create and maintain high-quality documentation effortlessly, with a bunch of amazing features like automated AI search functionality, easily customisable styles, automatically generated API refrences and much more. With all these features in mind, naturally you'd want to know how you can migrate from your current Doc provider, namely Docusaurus, to Mintlify, luckily this is a seemless and easy process which you'll be walked through in this guide.

## Table of Contents

- Migrating a Docusaurus project to Mintlify

  - [What You'll Need](#what-youll-learn)

- [Step 1: Creating an Account](#step-1-creating-a-mintlify-account)
  - [Installing Mintlify to GitHub](#installing-mintlify-to-github)
- [Step 2: Cloning the Installed Repo](#step-2-cloning-the-installed-repo)
- [Step 3: Migrating from Docsaurus](#step-3-migrating-from-docsaurus)
- [Step 4: Push Migration to Github](#step-4-push-migration-to-github)
- [Step 5: Finding Your Migrated Docs](#step-5-finding-your-updated-docs)

## What You'll Need

- Git
- Node.js
- npm

## Step 1: Creating a Mintlify Account

Head to [https://dashboard.mintlify.com/signup](https://dashboard.mintlify.com/signup) and follow the prompts create your account.

### Installing Mintlify to GitHub

Once you've created your Account you'll need to install the Mintlify GitHub App in your account, follow the prompts this should create a `Docs` ( or what you called it when you installed it ) Repo in your account, this repo is what we'll use for migration and you should be redirected to your [Dashboard](https://dashboard.mintlify.com/)

## Step 2: Cloning the Installed Repo

In your code editor clone the repo installed by Mintlify:

```bash
git clone <YOUR-INSTALLED-REPO-URL>
```

## Step 3: Migrating from Docsaurus

Once cloned, in the root folder run the following code with the URL to your website at the end

```bash
npx @mintlify/scraping@latest section <YOUR-WEBSITE-URL>
```

- Things to Look out for

  We noticed that sometimes empty `pages` values caused the deployment not work as expected. Open the `mint.json` file and remove any `group` keys with an empty `pages` key

  e.g

  ```json
    {
    "group": "Get Started/faq/",
    "pages": [""]
  },
  ```

  or

  ```json
  {
    "group": "Build/tools/"
  },
  ```

  should be removed

## Step 4: Push Migration to Github

Run the following to push the changes:

```bash
git add .
git commit -m "Migration From Docusaurus to Mintlify"
git push
```

## Step 5: Finding Your Updated Docs

Head to your [dashboard](https://dashboard.mintlify.com/) on Mintlify. There will be a button labelled `Visit Docs` , click on it and that will take you to your deployed documentation, succesfully migrated from Docusaurus
