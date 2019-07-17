# Todo svelte 3 app

![Project Image](/docs/images/app.png)

The sample Todo app is built using svelte 3.x framework

Demo: [todo svelte](http://todo-svelte.surge.sh)

Scaffolded using [degit](https://github.com/Rich-Harris/degit) tool with base template configured to use Rollup as bundler.

App Template: https://github.com/sveltejs/template

```bash

// Scaffold a svelte-app using degit
npx degit sveltejs/template svelte-app

// Change directory
cd svelte-app

// Install dependencies
npm install

// Run the project
npm run dev

```

### Deploying the app with [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public
```

If you are developing shareable components using svelte then use the official component template
[sveltejs/component-template](https://github.com/sveltejs/component-template)
