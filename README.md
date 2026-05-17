# Angular Developer Skill

A practical AI assistant skill for Angular development, code review, refactoring, debugging, and architecture guidance.

This skill is designed to help developers work with modern Angular applications using production-oriented patterns, readable TypeScript, accessibility, performance awareness, and maintainable architecture.

## What this skill does

This skill configures an AI assistant to act as an expert Angular developer and reviewer.

It focuses on:

- modern Angular development
- standalone components
- strict TypeScript
- signals and computed state
- RxJS best practices
- clean component boundaries
- maintainable services
- performance improvements
- accessibility checks
- practical testing guidance
- incremental refactoring
- debugging common Angular issues

The main goal is not to provide generic Angular explanations, but to give concrete, actionable recommendations with useful code examples.

## Default Angular assumptions

Unless specified otherwise, the skill assumes:

- modern Angular
- standalone components by default
- Angular CLI project structure
- TypeScript strict mode
- RxJS is available
- Signals are available
- new Angular control flow syntax is preferred:
  - `@if`
  - `@for`
  - `@switch`
- lightweight solutions are preferred over unnecessary abstractions
- large UI libraries should be avoided unless the project already uses one

## Main use cases

### Code review

Use this skill to review Angular components, services, templates, forms, state management, and feature architecture.

Example prompt:

```md
Review this Angular component. Focus on architecture, performance, accessibility, and state management. Suggest only practical improvements.
```

### Refactoring

Use this skill when you want to improve existing Angular code without rewriting everything from scratch.

Example prompt:

```md
Refactor this Angular feature incrementally. Preserve behavior, explain the risks, and show the improved code.
```

### Debugging

Use this skill to identify likely causes of Angular bugs and get minimal fixes before larger refactors.

Example prompt:

```md
Debug this Angular error. First identify the most likely cause, then give the smallest safe fix.
```

### Architecture decisions

Use this skill when deciding how to split components, introduce services, handle async state, or structure a feature.

Example prompt:

```md
Help me design the architecture for this Angular feature. Avoid overengineering and do not suggest NgRx unless it is really justified.
```

## Opinionated Angular preferences

This skill prefers:

- small focused components
- `ChangeDetectionStrategy.OnPush`
- standalone components
- `inject()` for dependency injection
- signals for local UI state
- `computed()` for derived state
- RxJS for async streams and cancellation
- typed reactive forms
- route-level lazy loading
- semantic HTML
- practical tests over brittle implementation tests

It avoids:

- blindly recommending NgRx
- converting everything to signals without reason
- nested subscriptions
- business logic in templates
- vague helper services
- large smart components
- abstract base classes without a clear need
- outdated Angular patterns for modern projects

## Recommended response formats

The skill uses structured responses when helpful.

For problem solving:

```md
## Problem

What is wrong or risky.

## Better approach

What should be changed and why.

## Example

Code example.

## Notes

Trade-offs, edge cases, or migration advice.
```

For refactoring:

```md
## Current issue

## Refactor plan

## Refactored code

## Why this is better

## Possible next step
```

## Example output

```md
## Problem

The component is doing too much: it loads data, stores UI state, filters results, and renders the table.

## Better approach

Split the feature into a page component, presentational components, an API service, and a small feature store.

## Example

- `BooksPageComponent` — coordinates the feature
- `BooksTableComponent` — renders the table
- `BooksFiltersComponent` — handles filter UI
- `BooksApi` — performs HTTP requests
- `BooksStore` — owns feature state

## Notes

Do not introduce NgRx unless the state is shared across distant features or the project already uses it.
```

## Installation

Copy the skill file into your assistant, agent, or coding workflow configuration.

For example, if your tool supports custom skills as Markdown files:

```bash
skills/
  angular-developer-skill.md
```

Then enable or reference the skill when working on Angular projects.

## Suggested repository structure

```text
.
├── README.md
├── angular-developer-skill.md
└── LICENSE
```

## File naming

Recommended file name:

```text
angular-developer-skill.md
```

## Usage examples

### Review a component

```md
Use the Angular Developer Skill.

Review this component and template. Focus on:
- component responsibility
- state duplication
- RxJS usage
- template readability
- accessibility
- performance

Return concrete improvements with code examples.
```

### Refactor a feature

```md
Use the Angular Developer Skill.

Refactor this Angular feature incrementally. Preserve behavior first. Avoid unnecessary abstractions. Prefer standalone components, signals for local state, and RxJS for async flows.
```

### Debug a bug

```md
Use the Angular Developer Skill.

I have this Angular error. Identify the likely cause first, then provide the smallest safe fix before suggesting a broader refactor.
```

### Improve performance

```md
Use the Angular Developer Skill.

Analyze this Angular screen for performance problems. Check list tracking, template expressions, repeated HTTP calls, lazy loading, subscriptions, and large dependencies.
```

## Good for

- Angular code reviews
- frontend architecture reviews
- refactoring legacy Angular code
- modern Angular migration guidance
- debugging component and DI issues
- improving RxJS streams
- introducing signals carefully
- improving templates and accessibility
- preparing code for production

## Not intended for

This skill is not intended to be a generic Angular tutorial.

It is optimized for practical engineering feedback, code review, and production-oriented Angular development.

## License

MIT License is a good default choice for this kind of public skill repository.

Add a `LICENSE` file if you want others to freely use, copy, modify, and distribute the skill.

## Contributing

Contributions are welcome.

Good improvements include:

- better Angular examples
- updated modern Angular practices
- more debugging patterns
- accessibility examples
- testing examples
- migration guidance
- real-world code review checklists

Please keep the skill practical and avoid adding overly theoretical explanations.

## Author

Created by [@nickkupriyanov](https://github.com/nickkupriyanov).
