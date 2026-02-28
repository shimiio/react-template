React, Vite, TypeScript + SWC, TailwindCSS

# 1

pnpm create vite

Project name:
│ vite-project

Select a variant:
│ TypeScript + SWC

Use Vite 8 beta (Experimental)?:
│ No

Install with pnpm and start now?
│ Yes

# 2

cd vite-project
pnpm install -D tailwindcss @tailwindcss/vite

# 3

pnpm approve-builds

# 4

delete `/src/App.css`, `/public/vite.svg`, `/src/assets`

# 5

add to `/vite.config.ts`:

```
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react-swc";
import tailwindcss from "@tailwindcss/vite";

// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: { alias: [{ find: "@", replacement: "/src" }] },
});
```

# 6

clean completely and add to `/index.css`:
@import "tailwindcss";

# 7

delete in `/src/App.tsx` all unnecessary

# 8

delete in `/index.html`:
<link rel="icon" type="image/svg+xml" href="/vite.svg" />
