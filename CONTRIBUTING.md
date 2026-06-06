# Contributing to Domain Name Prediction System

Thank you for your interest in contributing! We welcome contributions from everyone. This document provides guidelines and instructions for contributing to this project.

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment for all contributors.

## How to Contribute

### Reporting Bugs

1. **Check existing issues** first to avoid duplicates
2. **Use a clear title** that describes the bug
3. **Provide detailed description** including:
   - Steps to reproduce the issue
   - Expected behavior
   - Actual behavior
   - Screenshots or error messages (if applicable)
4. **Include environment details:**
   - Python version
   - Operating system
   - Relevant library versions

### Suggesting Enhancements

1. **Use a clear title** describing the enhancement
2. **Provide detailed description** of the proposed feature
3. **Explain the use case** and expected benefits
4. **Include examples** of how the feature would work

### Submitting Pull Requests

1. **Fork the repository** to your GitHub account
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/Domain-Name-Prediction.git
   cd Domain-Name-Prediction
   ```

3. **Create a branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix
   ```

4. **Make your changes** following the coding standards (see below)

5. **Test your changes** thoroughly:
   ```bash
   pytest
   # or manually verify in Jupyter notebook
   ```

6. **Commit your changes** with clear messages:
   ```bash
   git commit -m "Brief description of changes"
   ```

7. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

8. **Open a Pull Request** with:
   - Clear title describing the changes
   - Detailed description of what was changed and why
   - Reference to related issues (if any)
   - Screenshots or examples (if applicable)

## Development Setup

### Environment Setup

1. **Create virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Install development tools**:
   ```bash
   pip install black flake8 pytest
   ```

## Coding Standards

### Python Style Guide

- Follow PEP 8 guidelines
- Use 4 spaces for indentation (not tabs)
- Maximum line length: 100 characters
- Use meaningful variable and function names

### Code Formatting

Run code formatter before committing:
```bash
black .
```

### Linting

Check code quality:
```bash
flake8 .
```

### Documentation

- Add docstrings to all functions and classes
- Use clear comments for complex logic
- Keep documentation up-to-date with code changes

Example docstring:
```python
def extract_domain_features(domain_name):
    """
    Extract structural features from a domain name.
    
    Args:
        domain_name (str): The domain name to analyze
        
    Returns:
        dict: Dictionary containing extracted features
        
    Example:
        >>> features = extract_domain_features("example-domain.com")
        >>> print(features['length'])
        18
    """
    pass
```

### Jupyter Notebooks

- Keep notebooks well-organized with markdown cells
- Add comments explaining complex operations
- Clear output before committing (run `Cell > All Output > Clear`)
- Document data dependencies and sources

## Commit Guidelines

### Commit Messages

- Use clear, descriptive commit messages
- Start with imperative mood: "Add feature" not "Added feature"
- Limit subject line to 50 characters
- Add detailed body if necessary (wrap at 72 characters)
- Reference issues when applicable: "Fixes #123"

### Examples

```
Add domain age feature extraction

Implement calculation of domain registration age as a feature.
This includes parsing WHOIS dates and computing time deltas.

Fixes #45
```

## Pull Request Process

1. **Update documentation** if your changes affect usage
2. **Add tests** for new functionality
3. **Ensure all tests pass**
4. **Request reviews** from maintainers
5. **Address review comments** promptly
6. **Await approval** before merging

## Code Review

When reviewing PRs:
- Be respectful and constructive
- Focus on code quality, not personal style
- Suggest improvements clearly
- Approve when ready

## Areas for Contribution

### Code
- Bug fixes
- Feature implementations
- Performance improvements
- Test coverage

### Documentation
- README improvements
- Code comments and docstrings
- Usage examples
- Tutorial notebooks

### Data
- Dataset improvements
- Feature engineering suggestions
- Data quality enhancements
- Validation datasets

### Testing
- Unit tests
- Integration tests
- Test coverage improvement

## Questions?

- Check existing documentation
- Search for similar issues
- Open a discussion issue
- Comment on relevant PRs

## License

By contributing to this project, you agree that your contributions will be licensed under its MIT License.

## Recognition

Contributors are recognized in:
- Repository contributor list
- Release notes for their changes
- Project acknowledgments section

Thank you for contributing! 🎉
