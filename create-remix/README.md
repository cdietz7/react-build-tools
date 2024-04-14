# Create Remix

Tool for generating a "batteries included" installation.

# Installation

Create a plain Remix install:

```bash
npx create-remix@latest
```

Example output:

```ps1
PS G:\Websites\react-build-tools\remix> npx create-remix@latest
Need to install the following packages:
create-remix@2.8.1
Ok to proceed? (y) y

 remix   v2.8.1 💿 Let's build a better website...

   dir   Where should we create your new project?
         ./my-remix-app

      ◼  Using basic template See https://remix.run/guides/templates for more
      ✔  Template copied

   git   Initialize a new git repository?
         Yes

  deps   Install dependencies with npm?
         Yes

      ✔  Dependencies installed

      ✔  Git initialized

  done   That's it!

         Enter your project directory using cd .\my-remix-app
         Check out README.md for development and deploy instructions.

         Join the community at https://rmx.as/discord
```

# Running for Development

For our developing pleasure, Remix uses the lightning-fast Vite for development mode. To start:

```ps1
npm run dev
```

# Running for Production

First, build the project. If you don't, you'll see something like:

```ps1
PS G:\Websites\react-build-tools\remix\my-remix-app> npm run start

> start
> remix-serve ./build/server/index.js

Error: ENOENT: no such file or directory, stat 'G:\Websites\react-build-tools\remix\my-remix-app\build\server\index.js'
    at Object.stat (node:internal/fs/sync:58:25)
    at Object.statSync (node:fs:1669:17)
    at reimportServer (G:\Websites\react-build-tools\remix\my-remix-app\node_modules\@remix-run\serve\dist\cli.js:84:39)
    at run (G:\Websites\react-build-tools\remix\my-remix-app\node_modules\@remix-run\serve\dist\cli.js:113:21)
    at processTicksAndRejections (node:internal/process/task_queues:95:5)
```

To build, in the project directory run the command:

```ps1
npm run build
```

Example output:
```ps1
PS G:\Websites\react-build-tools\remix\my-remix-app> npm run build

> build
> remix vite:build

vite v5.2.8 building for production...
✓ 83 modules transformed.
build/client/.vite/manifest.json                1.02 kB │ gzip:  0.29 kB
build/client/assets/_index-D_UUquDl.js          0.76 kB │ gzip:  0.38 kB
build/client/assets/root-CdN9S7dO.js            1.44 kB │ gzip:  0.84 kB
build/client/assets/jsx-runtime-BlSqMCxk.js     8.09 kB │ gzip:  3.05 kB
build/client/assets/entry.client-CmAxv4Nw.js   57.28 kB │ gzip: 19.49 kB
build/client/assets/components-CT78CVRP.js    178.40 kB │ gzip: 57.07 kB
✓ built in 1.22s
vite v5.2.8 building SSR bundle for production...
✓ 5 modules transformed.
build/server/.vite/manifest.json  0.15 kB
build/server/index.js             6.84 kB
✓ built in 37ms
```

Then, the build can be run with:

```ps1
npm run start
```

# Resources

Remix Official Docs - Quick Start
https://remix.run/docs/en/main/start/quickstart

