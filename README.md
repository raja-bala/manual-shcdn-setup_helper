# React + TypeScript + Vite

# Install Vite in the current directory

```shell
npm create vite@latest ./
```

# Install and setup Tailwind CSS

```shell
npm install tailwindcss @tailwindcss/vite
```

**Replace everything in src/index.css with the following:**

```css
@import "tailwindcss";
```

**Edit tsconfig.json file**

```json
{
  "files": [],
  "references": [
    {
      "path": "./tsconfig.app.json"
    },
    {
      "path": "./tsconfig.node.json"
    }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

**Edit tsconfig.app.json file**

```json
{
  "compilerOptions": {
    // ...
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
    // ...
  }
}
```

**Update vite.config.ts file**

```shell
npm install -D @types/node
```

**_vite.config.ts_**

```ts
import path from "path";
import tailwindcss from "@tailwindcss/vite";
import react from "@vitejs/plugin-react";
import { defineConfig } from "vite";

// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
});
```

**Run the shadcn init command to setup your project:**

```shell
npx shadcn init
```
