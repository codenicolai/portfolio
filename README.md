# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```sh
# create a new project
npx sv create my-app
```

To recreate this project with the same configuration:

```sh
# recreate this project
npx sv create --template minimal --types ts --install yarn porfolio
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```sh
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```sh
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

## Deploying to GitHub Pages

This project uses [`adapter-static`](https://svelte.dev/docs/kit/adapter-static) to prerender the site into the `build/` directory, and [`gh-pages`](https://www.npmjs.com/package/gh-pages) to publish that directory to the `gh-pages` branch.

```sh
# 1. build the static site into build/
npm run build

# 2. publish build/ to the gh-pages branch on origin
npm run deploy
```

`npm run deploy` runs `gh-pages -d build --dotfiles`, which pushes the contents of `build/` (including dotfiles like `.nojekyll`) to the `gh-pages` branch. GitHub Pages serves that branch directly at [codenicolai.github.io](https://codenicolai.github.io).
