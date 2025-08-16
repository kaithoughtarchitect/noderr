# Installing Noderr

## Prerequisites

Before installing Noderr:
- You should have prepared your project vision (blueprint, project overview, architecture)
- You should have built an initial prototype based on those plans
- You should have Git initialized in your project

## Installation

### 1. Download Noderr

Download the latest release: [noderr-starter.zip](https://github.com/kaithoughtarchitect/noderr/releases/download/v1.9.1/noderr.starter.zip)

### 2. Add to Your Project

Extract the ZIP and add the `noderr` folder to your project:
- Drag and drop the folder into your project
- Upload the folder to your codebase (for cloud IDEs)
- Or extract directly in your project directory

That's it! You now have the Noderr framework in your project.

### 3. Run Install and Reconcile
Give your AI assistant this prompt:
```
noderr/prompts/ND__Install_And_Reconcile.md
```

### 4. Run System Audit
Verify everything is ready:
```
noderr/prompts/ND__Post_Installation_Audit.md
```
This ensures 100% architectural completeness and system readiness.

### 5. Review and Approve
When the AI pauses:
- Review audit report for any issues
- Address any critical gaps identified
- Confirm development readiness percentage

## Post-Installation
Once audit shows 100% readiness:
```
noderr/prompts/ND__Start_Work_Session.md
```

## What's Included

```
your-project/
└── noderr/                    # Everything inside!
    ├── noderr_project.md
    ├── noderr_architecture.md
    ├── noderr_tracker.md
    ├── noderr_log.md
    ├── noderr_loop.md
    ├── environment_context.md
    ├── specs/
    ├── planning/
    └── prompts/
```

## Documentation

- **Quick Start**: See [Getting Started Guide](./docs/noderr_getting_started.md)
- **Concepts**: See [Understanding Noderr](./docs/understanding-noderr.md)
- **Commands**: See [Prompts Guide](./docs/noderr_prompts_guide.md)

## Troubleshooting

### Common Issues

**Environment commands don't work**
- The `noderr/environment_context.md` file must be filled out during installation
- Test commands manually in your terminal
- Update the file with working commands

**AI seems confused**
- Ensure you've completed the full installation process
- Run `noderr/prompts/ND__Start_Work_Session.md` to sync
- Check that all files were properly updated

### Support

For issues or questions:
- Check the documentation links above
- Review the [Getting Started Guide](./docs/noderr_getting_started.md) for detailed instructions
- Open an issue on GitHub

---

*Note: Noderr is installed AFTER your initial build to document what actually exists, not just what was planned.*
