# react-template

## Stack
- React 19
- Vite
- TypeScript + React Compiler
- Tailwind CSS v4.2
- pnpm

## Setup

**1 - Create project**
```bash
pnpm create vite
# Project name: vite-project
# Select: React → TypeScript + React Compiler
```

**2 - Install Tailwind**
```bash
cd vite-project
pnpm install -D tailwindcss @tailwindcss/vite
```

**3 - Configure `vite.config.ts`**
```typescript
import { defineConfig } from "vite";
import react, { reactCompilerPreset } from "@vitejs/plugin-react";
import babel from "@rolldown/plugin-babel";
import tailwindcss from "@tailwindcss/vite"; // added

// https://vite.dev/config/
export default defineConfig({
  plugins: [
    react(),
    babel({ presets: [reactCompilerPreset()] }),
    tailwindcss(), // added
  ],
  resolve: { alias: [{ find: "@", replacement: "/src" }] }, // added
});
```

**4 - Configure `index.css`**
```css
@import "tailwindcss";
```

**5 - Cleanup**
- Delete `/src/App.css`, `/src/assets`
- Clean `App.tsx`

## Run
```bash
pnpm run dev
```
