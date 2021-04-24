# How to Install SCSS on Svelte with VSCode
Firstly, install the [Svelte for VSCode Extension](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode) if you're using VSCode. Next, open your terminal and write the following:

    npx degit sveltejs/template my-svelte-app
    cd my-svelte-app
    npm install -D svelte-preprocess
    npm install -D sass

Here we've created a new Svelte project under the folder `my-sevelte-app`. We've also installed `svelte-preprocess` and `sass`.

If you're using VSCode, create a `svelte.config.js` file in your ROOT directory. In our case, place it in the `my-svelte-app` folder.

Your `svelte.config.js` file should appear next to your `rollup.config.js` file.

## svelte.config.js
In your `svelte.config.js` file, copy and paste the following:

    const sveltePreprocess =  require('svelte-preprocess');
    
    module.exports = {
	    preprocess: sveltePreprocess()
    };

## rollup.config.js

In your `rollup.config.js` file, find the `export default` section and under the `plugins`, add the `preprocess` line below:

    svelte({
	    preprocess: sveltePreprocess(),
	    compilerOptions: {
    // enable run-time checks when not in production
		    dev: !production
	    }
    }),

Trouble finding it? It should be next to your `compilerOptions` line.

## SCSS is now ready!
We can now add `lang="scss"` to any of our `style` tags in Svelte and it should run SCSS.
