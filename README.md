# Statehub Official Sources

This repository contains the official module sources list for the Statehub game server platform. Developers can submit their modules to be included in the official registry through [pull requests](https://github.com/statehub-server/official-sources/pulls).

Statehub is a modular, scalable game server platform that supports multi-instance module spawning, load balancing, and real-time communication through WebSockets. It's designed for MMO applications and provides a plugin-based architecture for extending functionality.

## Module Registry

The [`sources.0.json`](sources.0.json) file contains the official list of approved Statehub modules that can be installed and used by server administrators.

## Submitting Your Module

To add your module to the official registry, follow these steps:

### 1. Prepare Your Module

Ensure your module meets the following requirements:

- **Module Structure**: Your module must have a valid `manifest.json` file and a license file
- **Distribution**: Module must be packaged as a `.zip` file
- **Release**: Module must be hosted on a publicly accessible URL (GitHub Releases recommended)
- **Testing**: Module should be thoroughly tested
- **(Recommended) Documentation**: Include proper README and usage instructions

### 2. Module Manifest Example

Your `manifest.json` should follow this structure:

```json
{
  "name": "@yournamespace/yourmodule",
  "version": "1.0.0",
  "description": "Description of your module",
  "author": "Your Name <your.email@example.com>",
  "entryPoint": "dist/index.js",
  "multiInstanceSpawning": false,
  "dependencies": []
}
```

### 3. Submit Pull Request

1. Fork this repository
2. Edit [`sources.0.json`](sources.0.json)
3. Add your module to the `repositories` object:
   ```json
   "@yournamespace.yourmodule": "https://github.com/yourusername/yourmodule/releases/download/v1.0.0/module.zip"
   ```
4. Don't add yourself to the maintainers object! (unless you want annoying emails)
5. Create a pull request with:
   - Clear description of your module
   - Link to module documentation
   - Testing instructions

### 4. Review Process

All submissions will be reviewed for:

- **Security**: Code review for potential security issues
- **Quality**: They must be useful modules for production environments, not just technical demos
- **Compatibility**: Compatibility with current Statehub API
- **Functionality**: Module works as described

## Module Naming Convention

Modules should follow the scoped package naming convention:
- `@namespace.modulename` (e.g., `@statehub.pingpong`, `@mycompany.sessions`)
- **We don't use slashes (/)!** Use a period to separate the namespace from the module name 
- Only use one period as namespace-name separator
- (Recommended) Namespace should be your GitHub username or organization name
- Module name should be short, descriptive and lowercase

## Guidelines

### Do's ✅
- Use [semantic versioning](https://semver.org/) (e.g., 1.0.0, 1.1.0, 2.0.0)
- Include comprehensive documentation if possible
- Test your module thoroughly
- Follow TypeScript best practices, and compile your modules to JavaScript
- Use meaningful commit messages in PRs

### Don'ts ❌
- Submit modules with known security vulnerabilities
- Include proprietary or copyrighted content without permission of the author(s)
- Submit modules that duplicate existing functionality without improvement
- Use offensive or inappropriate naming

## Support

- **Issues**: Open an issue in this repository for registry-related problems
- **Module Development**: Check the main Statehub documentation
- **Community**: Join our community discussions

## License

This registry is maintained under the MIT License. Individual modules may have their own licenses.

## Maintainers

- **Olivia Navarro** - nanom@riseup.net

---

**Note**: By submitting a module to this registry, you agree that your module will be publicly available and that you have the rights to distribute
