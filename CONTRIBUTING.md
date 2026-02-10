# Contributing Guide

Thank you for your interest in contributing to the File Organizer Skill project! We welcome all forms of contribution.

## How to Contribute

### Report Issues

If you find a bug or have a feature suggestion:

1. Check [Issues](https://github.com/lb-diei/SFO/issues) to ensure it hasn't been reported
2. Create a new Issue with:
   - Clear title
   - Detailed description
   - Steps to reproduce
   - Expected vs actual behavior
   - Environment (OS, Claude Code version, etc.)

### Submit Code

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Standards

- Keep code clean and simple
- Add necessary comments
- Follow existing file structure
- Update relevant documentation

### Skill File Format

The `skill.md` file should follow this structure:

```markdown
# Skill Name

## Overview
Brief description of the skill

## Trigger Conditions
When to use this skill

## Input Parameters
- Required parameters
- Optional parameters

## Execution Steps
1. Step one
2. Step two
...

## Error Handling
Handle common issues

## Output Results
Success output format

## Usage Examples
Provide specific examples
```

### Documentation Contributions

- Fix typos
- Improve clarity
- Add more examples
- Translate documentation

## Development Setup

1. Clone the repository:
```bash
git clone https://github.com/lb-diei/SFO.git
```

2. Copy the skill file to Claude Code skills directory:
```bash
cp skill.md ~/.claude/skills/
```

3. Test the skill in Claude Code

## Testing

Before submitting code, ensure:

- Functionality works with multiple file types
- Edge cases are handled correctly
- Error messages are clear
- Documentation is updated

## License

By contributing code, you agree that your contributions will be licensed under the MIT License.

## Contact

For questions:

- Submit an Issue
- Send an email

---

Thank you for your contribution!
