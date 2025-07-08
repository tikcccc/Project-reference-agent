# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a single-page HTML application called "Jarvis鹰眼" (Jarvis Eagle Eye) - an AI-powered project matching and tender analysis prototype.

The application provides a complete workflow for:

1. **File Upload & Analysis**: Upload tender documents (PDF, TXT, DOCX, CSV, XLSX, MD, PPTX, HTML) for AI analysis
2. **Project Matching**: Find and select relevant reference projects based on analysis results  
3. **Form Generation**: Create detailed project reports with editable forms for selected projects

## Common Commands

The main application (`agent.html`) requires no build process - open directly in a web browser for testing and development.

## Architecture

The application is built as a single HTML file (`agent.html`) containing:

- **Frontend**: Vanilla JavaScript with CSS Grid/Flexbox layout
- **UI Components**: Four main workflow steps (upload, analysis, selection, form editing)
- **Data Management**: In-memory JavaScript objects for project data and form state
- **Styling**: CSS custom properties for theming and responsive design

### Key Components
- `app-container`: Main flex container with sidebar and content area
- `sidebar`: Navigation with history and new analysis button  
- `main-content`: Dynamic content area showing different workflow steps

### Workflow Steps
1. **Upload Page** (`page-0`): File upload interface with language selection
2. **Analysis Page** (`page-1`): Display analysis results in card format
3. **Selection Page** (`page-2`): Project selection with preview panel
4. **Form Page** (`page-3`): Multi-form editing interface for selected projects

### Data Models
- `projects`: Array of reference projects with metadata (title, location, developer, etc.)
- `selectedProjects`: Set tracking user-selected projects
- `editedFormsData`: Map storing modified form data for each project

### Key Functions
- `goToStep(stepNumber)`: Navigate between workflow steps
- `populateProjectList()`: Render project selection interface
- `setupMultiFormPage()`: Initialize multi-form editing interface
- `displayProjectForm(projectId)`: Show form for specific project

## Development Workflow

1. Edit `agent.html` directly
2. Test in browser - no build process needed
3. Modify the `projects` array to add/remove reference projects
4. Update CSS custom properties in `:root` for theme changes

## File Structure

```
/
├── agent.html                  # Main application (single HTML file)
├── CLAUDE.md                   # This file
├── Jarvis鹰眼_PRD.md           # Product requirements document
├── draft/                      # Development prototypes
│   ├── form-interface.html
│   ├── project-selection.html
│   └── tender-analysis.html
└── reference/                  # UI mockups and requirements
    ├── ui picture/             # Screenshots and UI designs
    ├── workflow.png            # Workflow diagram
    └── *.pdf                   # Requirements and example documents
```