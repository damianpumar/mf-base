# Add new Microfrontend Package

```sh
npx degit damianpumar/mf-package <YOUR_PACKAGE_NAME>
```

# Replace .env file with

```sh
VITE_<YOUR_PACKAGE_NAME>=http://localhost:300X

ex: VITE_PACKAGE=http://localhost:3001
```

> NOTE: <YOUR_PACKAGE_NAME> should be capital letters

# Replace your package name in your package.json

# Configure vite.config.ts for microfrontend package

```ts
export default defineConfig({
  federation: {
    name: "package",
    exposes: {
      "./package": "./src/App.tsx",
    },
  },
  plugins: [react()],
});
```

> NOTE: if your package is the "HOST" should be something like that (without exposes):

```ts
export default defineConfig({
  federation: {
    name: "host",
  },
  plugins: [react()],
});
```

# Install dependencies

In your root project execute

```sh
pnpm install:all
```

# Start up your project

```sh
pnpm dev
```
