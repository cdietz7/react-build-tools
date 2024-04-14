# Vite

Arguably the best alternative to create-react-app for client-side-only applications.

# Installation

Create a plain Vite app (TypeScript + SWC).
Most projects use TypeScript to reduce type-related bugs,
and SWC for ultra-fast live compilation and updates for improved developer experience.

```bash
npm create vite@latest
```

Example output:
```ps1
PS G:\Websites\react-build-tools\vite> npm create vite@latest
Need to install the following packages:
create-vite@5.2.3
Ok to proceed? (y) y
√ Project name: ... my-vite-project
√ Select a framework: » React
√ Select a variant: » TypeScript + SWC

Scaffolding project in G:\Websites\react-build-tools\vite\my-vite-project...

Done. Now run:

  cd my-vite-project
  npm install
  npm run dev
```

As the instructions specify, next, navigate into your project folder
and run `npm install` to pull the latest dependencies. Unlike some installers
like CRA and create-next-app, Vite does not pull these dependencies for you.
Easy enough to do it ourselves, though.

```ps1
PS G:\Websites\react-build-tools\vite> cd my-vite-project && npm install

added 162 packages, and audited 163 packages in 15s

38 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

# Resources

Vite Official Documentation
https://vitejs.dev/guide/

Building For Production (Static hosting service)
https://vitejs.dev/guide/build
