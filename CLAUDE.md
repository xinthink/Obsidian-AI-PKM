# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Build and Development
- `npm run dev` - Start development with watch mode (uses esbuild to compile TypeScript)
- `npm run build` - Production build with type checking (`tsc -noEmit -skipLibCheck && node esbuild.config.mjs production`)
- `npm i` - Install dependencies

### TypeScript Development
- TypeScript configuration in `tsconfig.json` with strict null checks enabled
- Target ES6, module ESNext
- Uses esbuild for bundling with hot reload in dev mode

### Linting
- ESLint available: `eslint main.ts` or `eslint .` for all TypeScript files
- Install globally first: `npm install -g eslint`

## Project Architecture

### Obsidian Plugin Structure
This is an Obsidian plugin built with TypeScript that demonstrates:
- **Main Plugin Class**: `MyPlugin` extends Obsidian's `Plugin` class in `main.ts`
- **Modal Components**: `SampleModal` and `SearchModal` for user interactions
- **Settings Management**: `SampleSettingTab` with persistent storage
- **Commands and UI**: Ribbon icons, commands, and settings integration

### Key Components
- **Entry Point**: `main.ts` - contains plugin class, modals, and settings
- **Manifest**: `manifest.json` - plugin metadata (ID: "obsidian-pkm-plugin")
- **Build Config**: `esbuild.config.mjs` - bundler configuration with external Obsidian APIs
- **Styling**: `styles.css` - plugin-specific CSS

### Dependencies
- **Runtime**: `langchain` for AI/ML functionality
- **Development**: Standard Obsidian plugin toolkit (TypeScript, esbuild, Obsidian API types)
- **External APIs**: Obsidian API externalized in build (not bundled)

### Plugin Features
- Semantic search modal accessible via ribbon icon
- Sample command demonstrations
- Settings tab integration
- Persistent settings storage

### Development Workflow
1. Make changes to `main.ts` or other TypeScript files
2. Run `npm run dev` for automatic compilation
3. Reload Obsidian to test changes
4. Use `npm run build` before releases

## Installation in Obsidian
Copy `main.js`, `styles.css`, and `manifest.json` to your vault's `.obsidian/plugins/obsidian-pkm-plugin/` directory.