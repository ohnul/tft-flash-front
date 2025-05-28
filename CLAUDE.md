# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a Next.js 15.3.2 application using the App Router architecture with TypeScript, Tailwind CSS v4, and shadcn/ui components.

## Essential Commands
```bash
npm run dev      # Start development server with Turbopack on http://localhost:3000
npm run build    # Create production build
npm run start    # Start production server
npm run lint     # Run ESLint
```

## Architecture & Key Patterns

### Directory Structure
- `/src/app/` - Next.js App Router pages and layouts
- `/src/lib/` - Utility functions and shared code
- `/public/` - Static assets

### Component Development
- This project uses **shadcn/ui** (New York style theme) for component library
- Component utilities are in `src/lib/utils.ts` including the `cn()` function for className merging
- Use Tailwind CSS v4 with CSS variables for styling
- Icons are provided by `lucide-react`

### Import Aliases
- Use `@/` prefix for imports from the `src/` directory (e.g., `import { cn } from '@/lib/utils'`)

### Key Files
- `components.json` - shadcn/ui configuration
- `src/app/page.tsx` - Main landing page
- `src/app/layout.tsx` - Root layout with font configuration (uses Geist font family)
- `src/lib/utils.ts` - Contains `cn()` utility for className management