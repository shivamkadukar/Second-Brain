
**Commit Message Structure**
```bash
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Types - 

- `fix` - patches a bug in codebase (correlates with `PATCH` in [[Semantic Versioning]])
- `feat` - new feature to the codebase (correlates with `MINOR`)
- `BREAKING CHANGE` - `BREAKING CHANGE` as footer or `!` after type/scope (correlates with `MAJOR`)
				   Can be part of any type.
- [Other allowed type](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines) - `build, chore, ci, docs, style, refactor, perf, test`


Specification - 
 `scope` - must be noun describing a section of the codebase

Examples - 
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

```
feat(api)!: send an email to the customer when a product is shipped
```

```
docs: correct spelling of CHANGELOG
```

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```

## Reference

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/#summary)
