# Contributing to Nixe Brain

Thank you for considering a contribution to Nixe Brain!
This project thrives on community-driven improvements.

## Ways to Contribute

- **Bug reports:** Open an issue describing the problem and steps to reproduce
- **Documentation improvements:** Fix typos, clarify steps, add examples
- **New domain examples:** Add a new vertical under `examples/`
- **Template variations:** Propose new project instruction templates
- **Translations:** Translate docs to other languages (keep English as primary)

## Development Workflow

1. **Fork** the repository
2. **Create a branch** using the naming convention:
   - `docs/short-description` for documentation changes
   - `feat/short-description` for new features or examples
   - `fix/short-description` for corrections
3. **Make your changes** following the style guidelines below
4. **Commit** using [Conventional Commits](https://www.conventionalcommits.org/):
   - `docs: fix typo in notion-setup guide`
   - `feat: add finance domain example`
   - `fix: correct page ID placeholder format`
5. **Open a Pull Request** with a clear description of what changed and why

## Style Guidelines

### Markdown
- Use ATX headings (`#`, `##`, `###`)
- Keep line length under 100 characters where possible
- Use fenced code blocks with language identifiers
- Use relative links for internal references

### Content
- **Neutral language only:** no company names, personal names, or proprietary details
- **Domain examples must be generic:** use "Law Firm A", "Startup X", "Researcher"
- **Templates must use `{{PLACEHOLDER}}` syntax** for all values users must replace
- **English is the primary language** for all documentation and templates

### File naming
- Use kebab-case: `notion-setup.md`, `multi-user.md`
- Prefix docs with number: `04-notion-setup.md`
- Keep names short and descriptive

## Review Process

All PRs are reviewed for:
- Accuracy of instructions
- Neutrality (no personal or proprietary content)
- Consistency with existing style
- Completeness (no partial guides)

## Questions?

Open an issue with the `question` label.
