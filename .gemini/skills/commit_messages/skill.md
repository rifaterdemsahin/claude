This skill defines the git commit message standards for the repository. Use this skill whenever generating a commit message.

# Commit Message Standards
Use Conventional Commits format:
`<type>[optional scope]: <description>`

**Types**:
- `feat`: A new feature or new file.
- `fix`: A bug fix.
- `docs`: Documentation only changes.
- `style`: Changes that do not affect the meaning of the code.
- `refactor`: A code change that neither fixes a bug nor adds a feature.
- `chore`: Updating build tasks, package manager configs, etc.

**Rules**:
- Keep the summary line under 50 characters.
- Use imperative mood ("add feature" not "added feature").
- Do not end the summary line with a period.
