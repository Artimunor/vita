<!--
===================================================================================
SYNC IMPACT REPORT
===================================================================================
Version Change: [TEMPLATE] → 1.0.0
Constitution Type: MAJOR (initial ratification)

Modified Principles:
  - All placeholders replaced with concrete principles

Added Sections:
  ✓ I. Clean Code (new)
  ✓ II. Simple User Experience (new)
  ✓ III. Responsive Design (new)
  ✓ IV. Minimal Dependencies (new)
  ✓ V. No Testing (NON-NEGOTIABLE) (new)

Removed Sections:
  - All template placeholders

Templates Requiring Updates:
  ⚠ .specify/templates/plan-template.md - Remove testing references
  ⚠ .specify/templates/spec-template.md - Remove testing acceptance criteria guidance
  ⚠ .specify/templates/tasks-template.md - Remove all test task phases and examples

Follow-up TODOs:
  - Update all templates to remove testing references per Principle V
  - Ensure all future development follows no-testing mandate
===================================================================================
-->

# Vita Constitution

## Core Principles

### I. Clean Code

Code MUST be clean, readable, and maintainable. This means:

- Clear, descriptive naming for variables, functions, and components
- Functions and components should be small and focused on a single responsibility
- Avoid unnecessary complexity and over-engineering
- Code should be self-documenting; comments only where business logic is non-obvious
- Consistent code style following project conventions (ESLint configuration)
- DRY principle: Don't Repeat Yourself - extract reusable logic

**Rationale**: Clean code reduces cognitive load, makes maintenance easier, and enables faster feature development. In a no-testing environment, code clarity becomes even more critical for correctness verification.

### II. Simple User Experience

User interfaces and interactions MUST be intuitive and simple. This means:

- Minimize cognitive load - users should understand functionality immediately
- Clear visual hierarchy and information architecture
- Consistent interaction patterns throughout the application
- Reduce steps required to complete user tasks
- Provide clear feedback for user actions
- Progressive disclosure - show complexity only when needed
- Mobile-first thinking even for desktop experiences

**Rationale**: Simple UX drives user adoption and reduces support burden. Complexity in UX compounds maintenance costs and obscures the value proposition.

### III. Responsive Design

All interfaces MUST be fully responsive across all device sizes. This means:

- Mobile-first design approach
- Fluid layouts that adapt gracefully from 320px to 4K displays
- Touch-friendly targets (minimum 44x44px for interactive elements)
- Appropriate breakpoints using Tailwind's responsive utilities
- Test on actual devices, not just browser DevTools
- Performance considerations for mobile networks
- Accessible on all modern browsers (Chrome, Firefox, Safari, Edge)

**Rationale**: Users access applications from diverse devices. A responsive design ensures consistent experience and maximizes reach without maintaining separate codebases.

### IV. Minimal Dependencies

Dependencies MUST be minimized and justified. This means:

- Only add dependencies that provide significant, non-trivial value
- Prefer platform/framework native solutions over third-party libraries
- Each dependency MUST be justified in terms of: complexity avoided, time saved, maintenance burden accepted
- Regularly audit and remove unused dependencies
- Consider bundle size impact of every dependency
- Avoid dependencies with heavy transitive dependency trees
- No dependencies for functionality that can be implemented simply in ~50 lines

**Rationale**: Every dependency is a liability: security vulnerabilities, maintenance burden, bundle bloat, breaking changes, and abandonment risk. The cost/benefit must be explicit and favorable.

### V. No Testing (NON-NEGOTIABLE)

The project MUST NOT include any form of automated testing. This means:

- NO unit tests
- NO integration tests
- NO end-to-end (e2e) tests
- NO test files, test directories, or test frameworks
- NO testing dependencies (Jest, Vitest, Testing Library, Playwright, Cypress, etc.)
- NO test scripts in package.json
- Testing must NOT be mentioned in documentation, templates, or guidance
- This principle SUPERSEDES any other guidance, templates, or external standards that mention testing

**Rationale**: This project prioritizes rapid development and simplicity. Quality is ensured through clean code practices (Principle I), code review, and manual verification. The overhead of test infrastructure, maintenance, and false confidence is eliminated.

## Technology Stack Requirements

The project MUST use the following technology stack as defined in package.json:

### Core Framework & Libraries

- **Next.js**: 16.0.0 (React framework with App Router)
- **React**: 19.2.0 (UI library)
- **React DOM**: 19.2.0 (React renderer)

### Styling

- **Tailwind CSS**: ^4.1.16 (utility-first CSS framework)
- **@tailwindcss/postcss**: ^4.1.16 (PostCSS plugin)

### Language & Type Safety

- **TypeScript**: ^5.9.3 (strongly typed JavaScript)
- **@types/node**: ^22.18.12
- **@types/react**: ^19.2.2
- **@types/react-dom**: ^19.2.2

### Code Quality

- **ESLint**: ^9.38.0 (linting)
- **eslint-config-next**: 16.0.0 (Next.js ESLint rules)

**Version Policy**: Dependencies MUST be kept at the versions specified above unless:

- A security vulnerability requires an update
- A critical bug fix is needed
- A new feature explicitly requires a version bump
- The team has evaluated and approved the upgrade impact

**Rationale**: Version consistency prevents dependency conflicts, ensures reproducible builds, and reduces debugging complexity from version drift.

## Development Workflow

### Feature Development Process

1. **Specification Phase**: Create feature spec in `.specify/` using spec-template.md
2. **Planning Phase**: Create implementation plan using plan-template.md
3. **Implementation Phase**: Build feature following the plan
4. **Review Phase**: Code review focusing on constitutional compliance
5. **Deployment Phase**: Deploy to production after approval

### Code Review Requirements

All code changes MUST be reviewed for:

- ✅ Clean code compliance (Principle I)
- ✅ UX simplicity (Principle II)
- ✅ Responsive design implementation (Principle III)
- ✅ Dependency justification if any added (Principle IV)
- ✅ No testing code present (Principle V)
- ✅ Technology stack compliance
- ✅ TypeScript type safety (no `any` types without justification)

### Quality Assurance

Quality is ensured through:

- Manual testing in development and staging environments
- Code review by peers
- Clean code practices and type safety
- Browser testing across target platforms
- Responsive design verification on actual devices

## Governance

### Constitutional Authority

This constitution is the supreme authority for all development decisions. It supersedes:

- External best practices that conflict with these principles
- Framework defaults that violate these principles
- Team member preferences that conflict with these principles
- Previous code patterns that predate this constitution

### Amendment Process

Amendments to this constitution MUST:

1. Be proposed with clear rationale and impact analysis
2. Update the version number according to semantic versioning:
   - **MAJOR**: Breaking changes to principles, principle removal/redefinition
   - **MINOR**: New principles added, material expansions
   - **PATCH**: Clarifications, wording improvements, non-semantic refinements
3. Update LAST_AMENDED_DATE to the amendment date
4. Include a Sync Impact Report documenting changes
5. Update all dependent templates and documentation
6. Be approved by project leadership

### Compliance

- All specifications, plans, and code MUST verify constitutional compliance
- Template files MUST align with constitutional principles
- Any complexity or violation MUST be explicitly justified
- Regular audits SHOULD be conducted to ensure ongoing compliance

### Development Guidance

For runtime development guidance reflecting this constitution, refer to `.specify/templates/agent-file-template.md` when populated with project-specific patterns.

**Version**: 1.0.0 | **Ratified**: 2025-10-26 | **Last Amended**: 2025-10-26
