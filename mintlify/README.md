# Add Swytchcode to Mintlify

## Setup your development
To install Swytchcode on Mintlify, follow the steps below 
1. Obtain a [Chat API key](https://docs.swytchcode.com/modules/apikeys/#chat-api-key) from the web app.
2. Add the following iframe to the page
```html
<iframe src="https://PATH_TO_HOSTED_APP" width="1000" height="700"></iframe>
```
3. Add packages
```sh
npm install 
```
or
```sh
yarn
```

3. Test using
```
mint dev
```


# Swytchcode Chat Library

A powerful, customizable chat library that brings AI-driven code generation and assistance to your apps and docs—enabling your users to interact with your APIs directly and bypass traditional documentation.


## Features

- 🤖 AI-powered code generation and assistance
- 💬 Interactive chat interface
- 🎨 Customizable UI with theme support
- 🔌 Easy integration with any web application
- 📦 Available as UMD and ES modules
- 🌐 Works in both modern and legacy environments
- 🔍 Automatic language detection for code blocks
- 📝 Customizable input placeholder

## Installation

### NPM

```bash
npm install swytchcode
```

### Yarn

```bash
yarn add swytchcode
```

### CDN

```html
<script src="https://cdn.jsdelivr.net/gh/swytchcode/swytchcode-chat@v1.2.4/public/swytchcode.es.js"></script>
```

## Getting an API Key

Before using the library, you'll need an API key:

1. Visit [https://app.swytchcode.com](https://app.swytchcode.com)
2. Sign up or log in to your account
3. Go to Settings > Chat Key
4. Generate a new API key

## Usage

The `apiKey` prop is required for the library to function. You can pass it directly or use environment variables depending on your setup.

### ES Projects

```jsx
// pages/index.tsx or app/page.tsx
import { Swytchcode } from 'swytchcode';

export default function Home() {
  return (
    <Swytchcode
      apiKey="YOUR_API_KEY"
      borderColor="#3b82f6"
      height="600px"
      width="100%"
      initialMessage="Welcome to the Swytchcode Chat Library!"
    />
  );
}
```


### Vanilla JavaScript/HTML

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/prism.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/components/prism-typescript.min.js"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/themes/prism-twilight.min.css" rel="stylesheet" />
</head>
<body>
  <div id="chat-library"></div>
  <script type="module">
        // Import React and ReactDOM as ES modules
        import React from 'https://esm.sh/react@18.2.0';
        import ReactDOM from 'https://esm.sh/react-dom@18.2.0';
        
        // Import the Swytchcode component
        import {Swytchcode} from './swytchcode.es.js';

        try {
            // Initialize the component
            const root = ReactDOM.createRoot(document.getElementById('root'));
            console.log('Root element:', document.getElementById('root'));
            
            root.render(
                React.createElement(Swytchcode, {
                    apiKey: 'YOUR_API_KEY', // Replace with your actual API key
                    theme: 'twilight',
                    height: '80vh',
                    width: '100%',
                    initialMessage: "Hello! I'm your AI assistant. How can I help you today?"
                })
            );
        } catch (error) {
            console.error('Error in script:', error);
            document.getElementById('root').innerHTML = `<div style="color: red; padding: 1rem;">Error: ${error.message}</div>`;
        }
    </script>
</body>
</html>
```

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `apiKey` | string | undefined | Your Swytchcode API key (required) |
| `borderColor` | string | '#e5e7eb' | Color of the library border |
| `height` | string \| number | '80vh' | Height of the library |
| `width` | string \| number | '100%' | Width of the library |
| `initialMessage` | string | 'Hello! How can I help you today?' | Initial message displayed in the chat |
| `sendButtonColor` | string | '#2563eb' | Color of the send button |
| `userBubbleColor` | string | '#3b82f6' | Color of user message bubbles |
| `promptValue` | string | 'Ask me for code for any API method or full workflow...' | Placeholder text for the input field |
| `highlightTheme` | string | 'twilight' | Theme for code syntax highlighting |

## Available Prism Themes

The `highlightTheme` prop supports the following themes:

| Theme | Description |
|-------|-------------|
| `default` | Clean and minimal theme with a light background |
| `dark` | Dark theme with high contrast |
| `funky` | Vibrant theme with a dark background and colorful syntax |
| `okaidia` | Dark theme with a warm color palette |
| `twilight` | Dark theme with a cool color palette (default) |
| `coy` | Light theme with subtle colors |
| `solarizedlight` | Light theme based on the Solarized color scheme |
| `tomorrow` | Dark theme with a modern color palette |
| `atom-dark` | Dark theme inspired by Atom editor |
| `vs` | Light theme inspired by Visual Studio |
| `xonokai` | Dark theme with a warm, earthy color palette |
| `duotone-dark` | Dark theme with a duotone color scheme |
| `duotone-light` | Light theme with a duotone color scheme |
| `duotone-sea` | Dark theme with a sea-inspired duotone scheme |
| `duotone-space` | Dark theme with a space-inspired duotone scheme |
| `duotone-earth` | Dark theme with an earth-inspired duotone scheme |
| `duotone-forest` | Dark theme with a forest-inspired duotone scheme |
| `duotone-rose` | Dark theme with a rose-inspired duotone scheme |

Example usage:
```jsx
<Swytchcode
  apiKey="YOUR_API_KEY"
  highlightTheme="dark"  // Choose any theme from the list above
  // ... other props
/>
```

## Code Block Support

The library automatically detects and supports code blocks in various programming languages. When the API returns code, it will:

1. Detect the programming language from the response
2. Apply appropriate syntax highlighting
3. Display the code in a formatted block with:
   - Language indicator
   - Copy button
   - Syntax highlighting
   - Scrollable container

Supported languages:
- TypeScript
- Javascript
- Python
- Java
- Go
- C++
- C#
- Ruby
- PHP
- Swift
- Kotlin
- Rust
- Ruby
- C

## Development

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

## Support

[![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/zuSXSv5GWs)

For support, please:
- Join our [Discord community](https://discord.com/invite/zuSXSv5GWs)
- Open an issue in the GitHub repository

