# React Piano Keyboard Layout

A customizable piano keyboard layout component for React applications. This component renders a digital keyboard that can be colored and styled based on your requirements.

## Installation

```bash
# If installing from GitHub
npm install --save github:yourusername/react-piano-keyboard-layout

# Or if published to npm
npm install --save react-piano-keyboard-layout
```

## Usage

```jsx
import React, { useState } from "react";
import { Layout } from "react-piano-keyboard-layout";
import "react-simple-keyboard/build/css/index.css";

const MyKeyboardComponent = () => {
  // Example state
  const [keyboardState, setKeyboardState] = useState({
    activeKeyCodes: new Set(["KeyA"]),
    colorKeyboardMapping: {
      KeyA: { backgroundColor: "white", textColor: "black" },
      KeyW: { backgroundColor: "red", textColor: "white" },
      KeyS: { backgroundColor: "red", textColor: "white" },
      // ... more key mappings
    },
  });

  return (
    <div>
      <h2>My Piano Keyboard</h2>
      <Layout keyboardState={keyboardState} showLabels={true} />
    </div>
  );
};

export default MyKeyboardComponent;
```

> **Important:** This component requires the CSS file from react-simple-keyboard. Make sure to import it in your application:
>
> ```jsx
> import "react-simple-keyboard/build/css/index.css";
> ```

## Props

### `keyboardState`

An object containing the keyboard's current state with the following properties:

- `activeKeyCodes`: A Set of strings representing currently active keys. These keys will be displayed as "pressed" on the keyboard. Each key code should match the format in the standard DOM KeyboardEvent.code property (e.g., "KeyA", "Digit1").

- `colorKeyboardMapping`: An object mapping key codes to their visual representation with the following structure:
  ```typescript
  {
    [keyCode: string]: {
      backgroundColor: string; // Any valid CSS color
      textColor: string;       // Any valid CSS color
    }
  }
  ```

Example of a `keyboardState` object:

```javascript
{
  activeKeyCodes: new Set(['KeyA', 'Digit1']),
  colorKeyboardMapping: {
    KeyA: { backgroundColor: 'white', textColor: 'black' },
    KeyS: { backgroundColor: 'red', textColor: 'white' },
    KeyD: { backgroundColor: '#00fb47', textColor: 'black' },
    KeyF: { backgroundColor: '#9500b3', textColor: 'white' },
    KeyG: { backgroundColor: 'rgb(120, 120, 120)', textColor: 'white' },
    KeyH: { backgroundColor: '#03b9d5', textColor: 'black' },
    Digit1: { backgroundColor: 'white', textColor: 'black' },
    // ... more key mappings
  }
}
```

### `showLabels`

A boolean indicating whether to show the key labels on the keyboard.

- `true` (default): Shows the key labels (letters and numbers) on the keyboard.
- `false`: Hides the key labels, showing only the colored keys.

## Supported Keys

The component supports the following keys:

- Letters: A-Z (represented as "KeyA", "KeyB", etc.)
- Numbers: 0-9 (represented as "Digit0", "Digit1", etc.)
- Symbols: -, =, [, ], ;, ', ,, ., /

## TypeScript Support

This package includes TypeScript definitions. You can import the types as follows:

```typescript
import {
  Layout,
  ColorKeyboardMapping,
  ColorKeyInfo,
} from "react-piano-keyboard-layout";
```

## License

MIT
