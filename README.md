# Python-Gif-Ascii-Animator with JSON Generation

This project is a creative fork aimed at converting animated GIFs into ASCII representations, with an added twist: it now supports JSON generation for implementation in React components. This enhancement builds upon the original concept of animating ASCII art in the console, turning it into a versatile tool for web development projects.

Originally inspired by a fun side project to create a command line progress bar, this endeavor has evolved into something much more intriguing. It allows for any animated GIF to be broken down into separate frames, transformed into ASCII strings, and now, with the new feature, exported as JSON data. This data can easily be incorporated into a React component, enabling the creation of unique web animations.

## How to Implement the JSON in a React Component

To use the generated JSON in a React component, follow this simple example:

```jsx
import React, { useState, useEffect } from 'react';

const AsciiAnimation = ({ jsonData }) => {
  const [frame, setFrame] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setFrame(currentFrame => (currentFrame + 1) % jsonData.length);
    }, 100); // Adjust frame rate as needed

    return () => clearInterval(interval);
  }, [jsonData.length]);

  return (
    <pre>
      {jsonData[frame]}
    </pre>
  );
};

export default AsciiAnimation;
```

This example component cycles through the ASCII frames stored in the JSON array, creating a simple but effective animation. Implement this component within your React app to add a unique ASCII animation touch.

While the original project included sound capabilities through pygame's mixer, this fork has removed that feature in favor of focusing on visual representation and web integration. Thanks to the original creator [@tpoff](https://github.com/tpoff), for their foundational work on this project.
