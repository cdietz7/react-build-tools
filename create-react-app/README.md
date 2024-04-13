# Create React App (CRA)

Create React App (CRA) [was] the official scaffolding tool for React, offering a straightforward setup for new projects without needing to configure Webpack or Babel.

# Installation

Create a plain React app

```bash
Syntax: npx create-react-app [project name]
npx create-react-app plain
```

Example output:
```ps1
PS G:\Websites\react-build-tools> npx create-react-app plain
Need to install the following packages:
create-react-app@5.0.1
Ok to proceed? (y) y
npm WARN deprecated tar@2.2.2: This version of tar is no longer supported, and will not receive security updates. Please upgrade asap.

Creating a new React app in G:\Websites\react-build-tools\plain.

Installing packages. This might take a couple of minutes.
Installing react, react-dom, and react-scripts with cra-template...


added 1494 packages in 48s

258 packages are looking for funding
  run `npm fund` for details

Installing template dependencies using npm...

added 67 packages, and changed 1 package in 7s

262 packages are looking for funding
  run `npm fund` for details
Removing template package using npm...


removed 1 package, and audited 1561 packages in 2s

262 packages are looking for funding
  run `npm fund` for details

8 vulnerabilities (2 moderate, 6 high)

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.

Success! Created plain at G:\Websites\react-build-tools\plain
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd plain
  npm start

Happy hacking!
```

What I observed happens: NPM will download and install the packages to run the command,
then erase the packages from the roaming npm folder; or so mine appears empty after
running the command.

# Troubleshooting

In Windows, if you see an error like this:

```bash
npm ERR! code ENOENT
npm ERR! syscall lstat
npm ERR! path C:\Users\(your user)\AppData\Roaming\npm
npm ERR! errno -4058
npm ERR! enoent ENOENT: no such file or directory, lstat 'C:\Users\(your user)\AppData\Roaming\npm'
npm ERR! enoent This is related to npm not being able to find a file.
npm ERR! enoent
```

Simply create the npm folder in the Roaming directory.

# Resources:

Create React App official documentation
https://create-react-app.dev/

"How to Build a React App – A Walkthrough of the Many Different Ways"
https://www.freecodecamp.org/news/how-to-build-a-react-app-different-ways/

"Best-of React Web" by Lucas Masuch
https://github.com/LukasMasuch/best-of-react

"Stop Using Create React App" by Web Dev Simplified
https://www.youtube.com/watch?v=kvkAoCbTM3Q

"STOP Using Create React App" by Theo - t3․gg
https://www.youtube.com/watch?v=7m14f0ZzMyY

"Building a single-page application with Next.js and React Router" by Colin McDonnell
https://colinhacks.com/essays/building-a-spa-with-nextjs

"7 better ways to create a React app" by Fireship
https://www.youtube.com/watch?v=2OTq15A5s0Y
