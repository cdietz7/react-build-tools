# react-build-tools
For Denver React meetup

Presentation slide deck:
https://docs.google.com/presentation/d/16u4-BQVLyGWsGGwrdRgkNKb5RzhRgFH1hJiZ8CXqZFE/

# Comparisons

Comparisons were run on my local Windows 11 machine.

| spec | value |
| --- | --- |
| Processor | AMD Ryzen 7 3700X 8-Core Processor 3.60 GHz |
| Installed RAM | 32.0 GB |
| System type | 64-bit operating system, x64-based processor |
| npx npm and cache folders storage | C: drive (SSD) |
| cache | C:\Users\(Your User)\AppData\Local\npm-cache |
| npm npx | C:\Users\(Your User)\AppData\Roaming\npm |
| project files | G: drive (SSD). |

Commands were measured using Windows PowerShell Measure-Command.

Your results may vary; however, this should give an idea of relative build times.
Build times can help identify potential bottlenecks in CI/CD and help determine
whether some parts of the build process need cached somehow.

## Base Installation Time for Development

For our tests, the resulting project is a locally-runnable project
(generally using `npm run dev`).
Any further steps required to prepare a runnable project are included in the time.

I used the following PowerShell command to time installations with no npm cache.
- First, delete the npm-cache contents.
- Second, run the install command, pre-echoing required parameters.

Create-react-app

```ps1
Remove-Item -Path "C:\Users\$env:USERNAME\AppData\Local\npm-cache\*" -Recurse -Force
(Measure-Command { echo "y" | npx create-react-app plain }).TotalMilliseconds
```

Vite (React + TypeScript + SWC)

```ps1
Remove-Item -Path "C:\Users\$env:USERNAME\AppData\Local\npm-cache\*" -Recurse -Force
(Measure-Command {
    echo "y" `
    | npm create vite@latest plain -- --template react-swc-ts `
    && cd plain `
    && npm install
}).TotalMilliseconds
cd ../
```

Next.js (App Router project with the optional yet commonly-used bells-and-whistles)

```ps1
Remove-Item -Path "C:\Users\$env:USERNAME\AppData\Local\npm-cache\*" -Recurse -Force
(Measure-Command {
    echo "y" `
    | npx create-next-app@latest plain `
    --typescript `
    --eslint `
    --tailwind `
    --src-dir `
    --app `
    --import-alias "@/*"
}).TotalMilliseconds
```

Remix

```ps1
Remove-Item -Path "C:\Users\$env:USERNAME\AppData\Local\npm-cache\*" -Recurse -Force
(Measure-Command {
    echo "y" `
    | npx create-remix@latest plain `
    --install `
    --git-init `
    --yes
}).TotalMilliseconds
```

Gatsby

```ps1
Remove-Item -Path "C:\Users\$env:USERNAME\AppData\Local\npm-cache\*" -Recurse -Force
(Measure-Command {
    echo "y" `
     | npx gatsby new plain4 https://github.com/gatsbyjs/gatsby-starter-minimal-ts
}).TotalMilliseconds
```

Measured in Seconds

| Framework | Test 1  | Test 2  | Test 3  | Test 4  | Average Time (s) |
|-----------|---------|---------|---------|---------|------------------|
| CRA       | 60.077  | 62.674  | 54.945  | 56.176  | 58.468           |
| Vite      | 13.097  | 14.913  | 11.878  | 11.746  | 12.9085          |
| Next.js   | 29.752  | 37.248  | 25.835  | 36.126  | 32.24025         |
| Remix     | 54.121  | 52.102  | 82.327  | 53.931  | 60.62025         |
| Gatsby    | 130.587 | 140.118 | 299.482 | 136.570 | 176.689          |

NOTE: Times increase depending on number of people watching Instagram and TikTok videos
on your home network.

## Base Installation Storage Footprint

- CRA: 233 MB, 40,116 Files, 5,090 Folders
- Vite: 124 MB, 3,755 Files, 402 Folders
- Next.js: 294 MB, 17,197 Files, 1,841 Folders
- Remix: 174 MB, 17,375 Files, 2,238 Folders
- Gatsby: 524 MB, 48,436 Files, 7,158 Folders

## Build time for fresh project

Tested using:

```ps1
(Measure-Command { npm run build }).TotalMilliseconds
```

| Framework | Test 1    | Test 2     | Test 3     | Test 4     | Average Time (s) |
|-----------|-----------|------------|------------|------------|------------------|
| CRA       | 7.667     | 6.800**    | 6.871**    | 6.742**    | 7.020            |
| Vite      | 2.620     | 2.602      | 2.659      | 2.687      | 2.642            |
| Next.js   | 12.344    | 12.310     | 12.472     | 12.312     | 12.3595          |
| Remix     | 3.182     | 3.187      | 3.215      | 3.298      | 3.2205           |
| Gatsby    | 19.881    | 10.120***  | 10.368***  | 10.249***  | 12.6545          |

** I believe the CRAbuild caches some parts after the run,
thus the first number being 1 sec longer.
The first build also contained the error:

```
One of your dependencies, babel-preset-react-app, is importing the
"@babel/plugin-proposal-private-property-in-object" package without
declaring it in its dependencies. This is currently working because
"@babel/plugin-proposal-private-property-in-object" is already in your
node_modules folder for unrelated reasons, but it may break at any time.

babel-preset-react-app is part of the create-react-app project, which
is not maintianed anymore. It is thus unlikely that this bug will
ever be fixed. Add "@babel/plugin-proposal-private-property-in-object" to
your devDependencies to work around this error. This will make this message
go away.
```

*** Gatsby caches the build in "public" and ".cache" folders.
When I deleted these folders, build time resumed in being ~19 seconds.

## Build Folder Size

- CRA (/build): 544 KB, 15 Files, 4 Folders
- Vite (/dist): 147 KB, 5 Files, 1 Folder
- Next.js (.next): 29.5 MB, 96 Files, 25 Folders
- Remix (build): 264 KB, 8 Files, 3 Folders
- Gatsby (.cache): 30.6 MB, 356 Files, 51 Folders
- Gatsby (public): 1.10 MB, 33 Files, 10 Folders

## Features Configurable During Interactive

* Omitted CRA to focus on supported frameworks.

| Feature                   | vite  | create-next-app | create-remix | gatsby |
|---------------------------|-------|-----------------|--------------|--------|
| App Router                | -     | Yes             | -            | -      |
| Automatic sitemap         | -     | -               | -            | Yes    |
| CMS Integration           | -     | -               | -            | Yes    |
| ESLint                    | Auto  | Yes             | Auto         | -      |
| Google gtag               | -     | -               | -            | Yes    |
| Import alias customization| -     | Yes             | -            | -      |
| Initialize git repo       | -     | -               | Yes          | -      |
| Install dependencies      | -     | Auto            | Yes          | -      |
| Markdown + MDX            | -     | -               | -            | Yes    |
| Multiple CSS frameworks   | -     | -               | -            | Yes    |
| Optional src/             | -     | Yes             | -            | -      |
| Responsive images         | -     | -               | -            | Yes    |
| SWC                       | Yes   | -               | -            | -      |
| Tailwind CSS              | -     | Yes             | -            | Yes    |
| TypeScript                | Yes   | Yes             | Auto         | Yes    |





