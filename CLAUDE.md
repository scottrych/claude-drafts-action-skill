# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

The Claude Drafts Actions Skill is a comprehensive knowledge base and skill for Claude Code that enables assisting with Drafts app automation. Drafts is a powerful text capture and automation platform for iOS and macOS. This skill provides expert knowledge about creating and scripting custom actions, understanding all action step types, using templates, and JavaScript API integration.

## Project Structure

```
claude-drafts-action-skill/
├── README.md                      # Installation and usage guide
├── SKILL.md                       # Main skill documentation with core concepts
└── references/
    ├── action-steps-reference.md  # Detailed documentation for all 37+ action step types
    ├── scripting-api-reference.md # Complete JavaScript API reference
    └── template-tags-reference.md # Template system documentation
```

## Key Concepts

### Action Architecture

Actions are automation workflows consisting of sequential steps that process content and integrate with external services. Each action has:

1. **Metadata**: Name, icon (SF Symbols support), color, keyboard shortcuts
2. **Steps**: Sequential operations (System, Service, Utility, Advanced types)
3. **Configuration**: Post-execution behavior (archive, tag, notifications)

### Execution Triggers

- Action bars (keyboard shortcuts or action lists)
- External keyboard shortcuts
- URL schemes (`drafts://x-callback-url/runAction`)
- Scheduled automation via Shortcuts

### Step Categories

- **System Steps (11)**: Share, Clipboard, Mail, Message, Reminders, Calendar, Export, Print, etc.
- **Service Steps (22+)**: Dropbox, Google Drive, Notion, Todoist, WordPress, Mastodon, and others
- **Utility Steps (4)**: Draft creation, text insertion, template tags, UI configuration
- **Advanced Steps (9)**: JavaScript scripting, HTML previews, prompts, Shortcuts integration, URL schemes

### Template System

Templates use tag syntax with support for:
- Content tags: `[[draft]]`, `[[body]]`, `[[selection]]`
- Date/time formatting: `[[date|format]]` using strftime patterns
- Location data and custom tags
- Template modifiers for URL encoding and Markdown conversion
- External template files

### JavaScript API

The Drafts JavaScript API provides access to:
- **Draft object**: Content, metadata, tags, queries
- **Editor object**: Text manipulation, selection control
- **App object**: UI messages, navigation, clipboard
- **HTTP requests**: Network operations and service integrations
- **Service integrations**: Mail, Reminders, Calendar, file storage
- **Utility objects**: Prompt, HTMLPreview, FileManager

## Development Workflow

This is primarily documentation and reference material, not source code to be built or tested. When working with this skill:

1. **Updating References**: Edit `references/*.md` files when Drafts API or action step types change
2. **Expanding Examples**: Add real-world examples to SKILL.md and reference docs
3. **Maintaining Accuracy**: Verify examples work in current Drafts versions
4. **Cross-references**: Ensure internal links between SKILL.md and reference documents are consistent

## Common Tasks

### Adding New Action Step Documentation

1. Add documentation to `references/action-steps-reference.md`
2. Include: step name, description, configuration options, example use cases
3. Link from relevant section in SKILL.md

### Adding API Documentation

1. Update `references/scripting-api-reference.md`
2. Include: class/method signature, parameters, return types, examples
3. Group by object type (Draft, Editor, App, etc.)

### Adding Examples

1. Include complete, working code examples
2. Add context about when/why to use this approach
3. Consider adding both simple and advanced variations

## Reference Documentation

- [Drafts Official Website](https://getdrafts.com)
- [Drafts Documentation](https://docs.getdrafts.com)
- [Drafts Scripting Reference](https://scripting.getdrafts.com)
- [Drafts Action Directory](https://directory.getdrafts.com)

## Git Workflow

This repository follows standard practices:
- Main branch contains stable documentation
- Create feature branches for significant additions
- Commit messages should clearly describe documentation updates
