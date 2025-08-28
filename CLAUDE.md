# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page web application for "Purple Assistant BETA" - a Microsoft Teams-integrated help desk interface that uses ElevenLabs conversational AI. The project consists of a standalone HTML file with embedded CSS and JavaScript.

## Architecture

The application is built as a single HTML file (`index.html`) that:

1. **User Information Retrieval**: Attempts to get user details from Microsoft Teams context via Teams SDK, falling back to URL parameters
2. **ElevenLabs Integration**: Dynamically loads and configures an ElevenLabs conversational AI widget with user context
3. **Teams Compatibility**: Uses Microsoft Teams JavaScript SDK for seamless integration within Teams environment
4. **UI Theming**: Purple-themed color scheme matching corporate branding

### Key Components

- **User Context Detection**: Tries Teams context first, then SSO token, then URL parameters
- **JWT Token Decoding**: Client-side JWT parsing for user authentication
- **Dynamic Widget Loading**: Runtime loading of ElevenLabs widget with user variables
- **Attribution Hiding**: Aggressive CSS rules to hide ElevenLabs branding (including shadow DOM handling)

## Configuration

- **Agent ID**: Currently hardcoded as `agent_4901k3gjds1eexs83j5a7pv4xaaz`
- **Widget Position**: Fixed bottom-right positioning
- **Color Variables**: CSS custom properties for consistent theming

## Development

Since this is a static HTML file, no build process is required. Simply open `index.html` in a browser or serve it via a web server.

### Testing

For Teams integration testing, the application should be loaded within Microsoft Teams context. For local testing, you can append an `email` parameter to the URL.

## Deployment

This is a static web application that can be served from any web server or CDN. No server-side processing is required.