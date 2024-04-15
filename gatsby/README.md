# Gatsby

Excellent tool for building static websites with a GraphQL-powered data layer,
particularly for blogs, e-commerce, and documentation.

At the time of this writing, Gatsby supports the following CMS's:

- Contentful
- DatoCMS
- Netlify CMS
- Sanity
- Shopify
- WordPress

...And the following CSS frameworks:

- Emotion
- PostCSS
- Sass
- styled-components
- Theme UI
- vanilla-extract
- Tailwind CSS

Additional plugins include:

- Google gtag script for Google Analytics
- Responsive images
- Automatic sitemap
- Manifest file
- Markdown and MDX support (JavaScript variable placeholders)
- Markdown support (without MDX)

# Installation

Create a plain Gatsby project:

```bash
npm init gatsby
```

Example output:

```ps1
PS G:\Websites\react-build-tools\gatsby> npm init gatsby
create-gatsby version 3.13.1

                        Welcome to Gatsby!

This command will generate a new Gatsby site for you in G:\Websites\react-build-tools\gatsby with the setup you select. Let's answer some questions:


What would you like to call your site?
√ · My Gatsby Site
What would you like to name the folder where your site will be created?
What would you like to name the folder where your site will be created?
What would you like to name the folder where your site will be created?
√ gatsby/ my-gatsby-site2
√ Will you be using JavaScript or TypeScript?
· TypeScript
√ Will you be using a CMS?
· No (or I'll add it later)
√ Would you like to install a styling system?
· No (or I'll add it later)
√ Would you like to install additional features with other plugins?No items were selected


Thanks! Here's what we'll now do:

    Create a new Gatsby site in the folder my-gatsby-site2

√ Shall we do this? (Y/n) · Yes
√ Created site from template
√ Installed Gatsby
√ Installed plugins
√ Created site in my-gatsby-site2
Your new Gatsby site My Gatsby Site has been successfully created
at G:\Websites\react-build-tools\gatsby\my-gatsby-site2.
Start by going to the directory with

  cd my-gatsby-site2

Start the local development server with

  npm run develop

See all commands at

  https://www.gatsbyjs.com/docs/reference/gatsby-cli/
```

Or, installation can be complete without prompts by using a "starter".

See official starter packages: https://github.com/orgs/gatsbyjs/repositories?q=gatsby-starter-

```ps1
npx gatsby new my-gatsby-ts-site https://github.com/gatsbyjs/gatsby-starter-minimal-ts
```

I'm using the starter here for benchmarking purposes. If you need a more-custom setup;
for example, TypeScript with a specific CSS package and a specific plugin, you may prefer
to use the interactive CLI to customize your project.

## Troubleshooting

If you happen to see lots of errors that look like this:

```ps1
(node:15424) MaxListenersExceededWarning: Possible EventEmitter memory leak detected.
11 close listeners added to [TLSSocket]. Use emitter.setMaxListeners() to increase limit
```

...try upgrading Node.js and NPM if you're not on the latest version.

# Resources

Github
https://github.com/gatsbyjs/gatsby

Gatsby Open Source Documentation
https://www.gatsbyjs.com/docs

Deploy & Hosting
https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/

GraphQL
https://graphql.org/

"The End Of My Gatsby Journey"
https://www.smashingmagazine.com/2024/03/end-of-gatsby-journey/
