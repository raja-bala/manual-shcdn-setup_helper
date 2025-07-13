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

### Components

1. Add side bar

```shell
npx shadcn@latest add sidebar
```

2. Add check box

```shell
npx shadcn@latest add checkbox
```

3. Add form

```shell
npx shadcn@latest add form
```

4. Add date picker
   The Date Picker is built using a composition of the <Popover /> and the <Calendar /> components.
   To customsize Calender component we need **React Daypicker**, Calendar component is built on top of **React Daypicker**

```shell
npx shadcn@latest add popover
npx shadcn@latest add calendar
```

5. Add radio group

```shell
npx shadcn@latest add radio-group
```

6. Add select

```shell
npx shadcn@latest add select
```

6. Add Textarea

```shell
npx shadcn@latest add textarea
```

7. Add card

```shell
npx shadcn@latest add card
```

8. Add DataTable

```shell
npx shadcn@latest add table
```

Add tanstack/react-table dependency:

```shell
npm install @tanstack/react-table
```

9. Add combobox
   The Combobox is built using a composition of the <Popover /> and the <Command /> components.

```shell
npx shadcn@latest add command
```

10. Add Menubar

```shell
npx shadcn@latest add menubar
```

11. Add pagination

```shell
npx shadcn@latest add pagination
```

12. Add sidebar-08

comment everything from `App.css` including #root design

```shell
npx shadcn@latest add sidebar-08

```

had this error
[bug]: The requested module 'class-variance-authority' does not provide an export named 'VariantProps'
[fix from this link](https://github.com/shadcn-ui/ui/issues/6618)
**Fix**
The fix was to go into components/ui/sidebar.tsx and change the import from:

```tsx
import { VariantProps, cva } from "class-variance-authority";
```

To

```tsx
import { type VariantProps, cva } from "class-variance-authority";
```
