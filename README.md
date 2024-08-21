# Another Simple Experiment to get Tailwind, Typescript and Threlte running in SvelteKit

This Repository contains some of the source code from the Svelte Summit 2023 talk "Threlte 6" by Grischa Erbe.

I modified it a bit as a learning experience. 

## Creation
```bash
pnpm create svelte@latest threlte-conference-ticket
cd threlte-conference-ticket
pnpm i
pnpm i three @threlte/core @threlte/extras @types/three
pnpm i -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
Note that the `glb` model was created with the following command:

```bash
npx @threlte/gltf@1.0.0-next.12 ./Ticket.glb -t
```

It seems the `glb` format for models is the way to go.

And `Ticket.svelte` is auto-generated by: https://github.com/threlte/threlte/tree/main/packages/gltf

## Postcss config file:

```bash
# postcss.config.js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}

```

## Tailwind config file:

```bash
# tailwind.config.js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    './src/**/*.{svelte,html,js,ts}',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

```

## Building

To create a production version of your app:

```bash
pnpm run build
```

You can preview the production build with `pnpm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment. I used the `vercel` adapter as I deploy to `vercel`. It is fairly easy to do so.

> You may get `pnpm` from [here](https://pnpm.io) or `brew install pnpm` if you use `homebrew`