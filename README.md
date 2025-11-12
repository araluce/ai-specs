# AI Specifications & Development Rules

This repository contains a comprehensive set of development rules, standards, and AI agent configurations designed to work seamlessly with multiple AI coding copilots. The setup is portable and can be imported into any project to provide consistent, high-quality AI-assisted development.

## 📁 Repository Structure

```
.
├── ai-specs/                    # Main directory with all rules and configurations
│   ├── specs/                   # Development standards and specifications
│   │   ├── base-standards.mdc   # Core development rules (single source of truth)
│   │   ├── backend-standards.mdc
│   │   ├── documentation-standards.mdc
│   │   ├── development_guide.md
│   │   └── prompts.md           # Reusable prompt templates
│   └── changes/                 # Feature implementation plans
│
├── AGENTS.md                    # Generic agent configuration
├── CLAUDE.md                    # Claude-specific configuration
├── codex.md                     # GitHub Copilot/Codex configuration
└── GEMINI.md                    # Gemini-specific configuration
```

## 🤖 Multi-Copilot Support

This repository uses **symbolic links** or **naming conventions** to support multiple AI coding copilots without duplication:

- **`AGENTS.md`** → Generic agent rules (works with most copilots)
- **`CLAUDE.md`** → Optimized for Claude/Cursor
- **`codex.md`** → Optimized for GitHub Copilot/Codex
- **`GEMINI.md`** → Optimized for Google Gemini

All these files reference the same core rules in `ai-specs/specs/base-standards.mdc`, ensuring consistency across different AI tools while allowing copilot-specific customizations.

### Why This Approach?

✅ **Single Source of Truth**: Core rules maintained in one place (`base-standards.mdc`)
✅ **Copilot Compatibility**: Each AI tool finds its configuration using its preferred naming convention
✅ **Zero Configuration**: Import into a new project and it works immediately
✅ **Easy Updates**: Update rules once, all copilots benefit
✅ **Portable**: Copy this structure to any project

## 🚀 Quick Start

### 1. Import Into Your Project

```bash
# Clone or copy this repository into your project
cp -r ai-specs/* your-project/

# The AI copilot will automatically detect the relevant configuration file
```

### 2. Verify Configuration

Your AI copilot will automatically load:
- **Claude/Cursor**: `CLAUDE.md` → `ai-specs/specs/base-standards.mdc`
- **GitHub Copilot**: `codex.md` → `ai-specs/specs/base-standards.mdc`
- **Gemini**: `GEMINI.md` → `ai-specs/specs/base-standards.mdc`

All paths and rules are configured to work seamlessly without manual adjustments.

## 💡 Usage: Command-Based Development Workflow

The most efficient way to work with this setup is using a two-step command workflow:

### Step 1: Plan the Feature

Use **`plan-ticket`** commands to generate detailed implementation plans:

```
/plan-backend-ticket SCRUM-10
```

or

```
/plan-frontend-ticket SCRUM-15
```

This creates a comprehensive, step-by-step implementation plan in `ai-specs/changes/`.

### Step 2: Implement the Feature

Reference the generated plan and execute:

```
develop-backend @SCRUM-10_backend.md
```

or

```
develop-frontend @SCRUM-15_frontend.md
```

The AI will follow the plan precisely, implementing each step with TDD, proper testing, and documentation updates.

### Example: Implementing SCRUM-10 (Position Update Feature)

#### Step 1: Generate the Plan

**You say:**
```
/plan-backend-ticket SCRUM-10
```

**AI generates:**
- Analyzes the ticket requirements
- Creates `ai-specs/changes/SCRUM-10_backend.md` with:
  - Architecture context
  - Step-by-step implementation instructions
  - Complete test specifications (validation, service, controller layers)
  - API documentation updates
  - Validation rules
  - Error handling strategies

#### Step 2: Implement Following the Plan

**You say:**
```
/develop-backend @SCRUM-10_backend.md
```

**AI executes:**
1. Creates feature branch `feature/SCRUM-10-backend`
2. Implements validation function with comprehensive rules
3. Implements service layer with business logic
4. Implements controller with HTTP handling
5. Adds route configuration
6. Writes 90%+ test coverage across all layers
7. Updates API documentation
8. Runs tests and verifies implementation
9. Commits and pushes (configurable to wait until confirmation)

### 📋 Demo Implementation Plan

Check out **`ai-specs/changes/SCRUM-10_backend.md`** for a complete example of what a feature implementation plan looks like. This comprehensive plan includes:

- **Architecture Context**: Layers, components, and dependencies
- **Step-by-Step Instructions**: Validation → Service → Controller → Routes → Tests → Documentation
- **Complete Code Examples**: Full implementations for each layer
- **Comprehensive Test Specifications**: 90%+ coverage requirements with example tests
- **Error Handling**: HTTP status codes, error messages, and response formats
- **Business Rules**: Validation requirements and constraints
- **Testing Checklist**: Unit, manual, integration, and regression tests

This plan demonstrates how detailed and actionable the generated plans are, enabling autonomous implementation by AI agents.

## 📖 Core Development Rules

All development follows principles defined in `ai-specs/specs/base-standards.mdc`:

### Key Principles

1. **Small Tasks, One at a Time**: Baby steps, never skip ahead
2. **Test-Driven Development (TDD)**: Write failing tests first
3. **Type Safety**: Fully typed code (TypeScript)
4. **Clear Naming**: Descriptive variables and functions
5. **English Only**: All code, comments, documentation, and messages in English
6. **90%+ Test Coverage**: Comprehensive testing across all layers
7. **Incremental Changes**: Focused, reviewable modifications

### Specific Standards

- **Backend Standards**: `ai-specs/specs/backend-standards.mdc`
  - API development patterns
  - Database best practices
  - Security guidelines
  - Testing requirements

- **Frontend Standards**: `ai-specs/specs/frontend-standards.mdc`
  - React component patterns
  - UI/UX guidelines
  - State management
  - Component testing

- **Documentation Standards**: `ai-specs/specs/documentation-standards.mdc`
  - Technical documentation structure
  - API documentation (OpenAPI)
  - Code documentation
  - Maintenance guidelines

## 🔧 Customization

### Adapting to Your Project

1. **Update `base-standards.mdc`**: Modify core principles to match your needs
2. **Add Domain Rules**: Include project-specific business rules
3. **Extend Standards**: Add technology-specific guidelines (Vue, Angular, etc.)
4. **Create Templates**: Add prompt templates in `prompts.md`
5. **Link Resources**: Reference your project's specific documentation

### Maintaining Standards

- **Single Source of Truth**: Always update `base-standards.mdc` first
- **Version Control**: Track changes to standards like code
- **Team Review**: Standards changes should be reviewed like pull requests
- **Documentation**: Keep examples current with actual implementation
