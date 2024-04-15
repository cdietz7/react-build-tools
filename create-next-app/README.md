# Create Next App
For building Next.js apps. Officially supported by the Next.js team.

# Installation

Create a plain Next.js app

```bash
npx create-next-app@latest
```

Example output:

```ps1
PS G:\Websites\react-build-tools\next-js> npx create-next-app@latest
√ What is your project named? ... my-plain-project
√ Would you like to use TypeScript? ... No / Yes
√ Would you like to use ESLint? ... No / Yes
√ Would you like to use Tailwind CSS? ... No / Yes
√ Would you like to use `src/` directory? ... No / Yes
√ Would you like to use App Router? (recommended) ... No / Yes
√ Would you like to customize the default import alias (@/*)? ... No / Yes
Creating a new Next.js app in G:\Websites\react-build-tools\next-js\my-plain-project.

Using npm.

Initializing project with template: app-tw


Installing dependencies:
- react
- react-dom
- next

Installing devDependencies:
- typescript
- @types/node
- @types/react
- @types/react-dom
- postcss
- tailwindcss
- eslint
- eslint-config-next

(node:14556) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 close listeners added to [TLSSocket]. Use emitter.setMaxListeners() to increase limit
(Use `node --trace-warnings ...` to show where the warning was created)
(node:14556) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 close listeners added to [TLSSocket]. Use emitter.setMaxListeners() to increase limit
...{more occurrences of MaxListenersExceededWarning}...

added 360 packages, and audited 361 packages in 32s

133 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
Success! Created my-plain-project at G:\Websites\react-build-tools\next-js\my-plain-project
```

# Running for Development

Simply use the command in the project:

```ps
npm run dev
```

# Running for Production

Before starting, build the project using `npm run build` in the project directory.
If you dont, you may see something like...

```ps1
PS G:\Websites\react-build-tools\next-js\plain2> npm run start

> plain2@0.1.0 start
> next start

  ▲ Next.js 14.2.1
  - Local:        http://localhost:3000

 ✓ Starting...
Error: Could not find a production build in the '.next' directory. Try building your app with 'next build' before starting the production server. https://nextjs.org/docs/messages/production-start-no-build-id
    at setupFsCheck (G:\Websites\react-build-tools\next-js\plain2\node_modules\next\dist\server\lib\router-utils\filesystem.js:151:19)
    at async initialize (G:\Websites\react-build-tools\next-js\plain2\node_modules\next\dist\server\lib\router-server.js:61:23)
    at async Server.<anonymous> (G:\Websites\react-build-tools\next-js\plain2\node_modules\next\dist\server\lib\start-server.js:249:36)
```

Once the project's built, run `npm run start` in the production environment.

# Resources

create-next-app parameters:
https://nextjs.org/docs/app/api-reference/create-next-app
