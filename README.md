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

Install the package:

```bash
pnpm add morfik-pl
```

Import components:

```tsx
import { Button, Badge, Input, Card } from "morfik-pl";
import "morfik-pl/styles.css";
```

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

```bash
# Build the package
pnpm build

# Publish
pnpm publish
```

## Deploy Storybook to Vercel

Connect the repository to Vercel. The `vercel.json` config handles the rest automatically.

## License

MIT
