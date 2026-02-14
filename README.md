# morfik-pl

A React pattern library built with **Tailwind CSS**, **Radix UI**, and **shadcn/ui**. Documented with **Storybook** and hosted on **Vercel**.

## Tech Stack

- **React 19** + **TypeScript**
- **Tailwind CSS v4**
- **Radix UI** / **shadcn/ui** components
- **Storybook 8** for component documentation
- **tsup** for npm package build
- **pnpm** as package manager
- **Vercel** for Storybook hosting

## Getting Started

```bash
# Install dependencies
pnpm install

# Start Storybook dev server
pnpm dev

# Build the npm package
pnpm build

# Build Storybook for production
pnpm build:storybook
```

## Using as an npm package

In another project (React, Next.js, Vite, etc.):

```bash
pnpm add morfik-pl
```

Import components and styles (order matters: import styles first or at app entry):

```tsx
import "morfik-pl/styles.css";
import { Button, Badge, Input, Card, CardHeader, CardTitle, CardContent, CardFooter, cn } from "morfik-pl";

export function App() {
  return (
    <Card>
      <CardHeader>
        <CardTitle>Example</CardTitle>
      </CardHeader>
      <CardContent>
        <Button>Click</Button>
        <Badge variant="secondary">Badge</Badge>
      </CardContent>
    </Card>
  );
}
```

The package also exports variants (e.g. `buttonVariants`, `badgeVariants`) and the `cn` helper. Styles are precompiled (Tailwind v4), so you don't need to configure Tailwind in the consuming project.

## Project Structure

```
morfik-pl/
├── .storybook/          # Storybook configuration
├── src/
│   ├── components/
│   │   └── ui/          # shadcn/ui components
│   ├── lib/
│   │   └── utils.ts     # Utility functions (cn)
│   ├── stories/         # Storybook stories
│   ├── styles/
│   │   └── globals.css  # Tailwind CSS + design tokens
│   └── index.ts         # Package entry point
├── tsup.config.ts       # Build configuration
├── vercel.json          # Vercel deployment config
└── package.json
```

## Adding New Components

1. Create the component in `src/components/ui/`
2. Export it from `src/components/ui/index.ts`
3. Create a story in `src/stories/`
4. Run `pnpm dev` to preview in Storybook

## Publishing to npm

### Prerequisites

1. **npm account**: create an account at [npmjs.com](https://www.npmjs.com/signup) if you don't have one.
2. **Package name**: the name `morfik-pl` may already be taken on npm. Check [npmjs.com/package/morfik-pl](https://www.npmjs.com/package/morfik-pl). If taken, change the `"name"` in `package.json` (e.g. `@your-username/morfik-pl` for a scoped package).
3. **Repository** (optional): in `package.json` you can set `"repository": { "type": "git", "url": "https://github.com/your-username/morfik-pl.git" }` to link the npm page to your repo.

### Publishing

```bash
# Login (first time only; prompts for username, password, email)
npm login

# Build (outputs dist/ with JS, types and styles.css)
pnpm build

# Publish to npm (use --access public if using a scope, e.g. @your-username/morfik-pl)
pnpm publish
```

The `prepublishOnly` script runs `pnpm build` before every publish, so you can also run `pnpm publish` directly after logging in.

## Deploy Storybook to Vercel

Connect the repository to Vercel. The `vercel.json` config handles the rest automatically.

## License

MIT
