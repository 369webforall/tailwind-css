# tailwind-css

Tailwind css

Content

- Colors
- Backgrounds
- Borders
- Typography
- Spacing
- Sizing
- Flex
- Grid
- Layouts
- Effects
- Filters
- Transitions & Animation
- Transforms

# Video

[tailwind-css-5-29-2023](https://youtu.be/NdELGgWDBnk)

[tailwind-css-5-30-2023](https://youtu.be/Zg-nesIA3jI)

[tailwind-css-5-31-2023](https://youtu.be/q1IFvTukZzE)

# Installation and setup tailwind in your React App

- Install Reat App using vite ` npm create vite@latest`
- Give project name, select React and javaScript
- After installed, change to project directory in your terminal
- `cd my-app`
- `npm install`
- Now setup the tailwind
  [Tailwind CSS setup Link](https://tailwindcss.com/docs/guides/vite)

- setp -2 Install Tailwind CSS

`Install tailwindcss and its peer dependencies, then generate your tailwind.config.js and postcss.config.js files`

```javascript
  npm install -D tailwindcss postcss autoprefixer
  npx tailwindcss init -p
```

- step 3- Configure your template paths
- copy the below code to tailwind.config.js file

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

- step -4 Add the Tailwind directives to your CSS
  add below code to index.css

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- now run your project `npm run dev`

# Tutorial

Why not just use inline styles?
Why Trailwind css is more superior then inline styles.

1. **Separation of concerns**: Tailwind CSS promotes a separation of concerns by keeping your HTML markup clean and focused on structure, while the styling is handled separately in the CSS. This makes your code more maintainable and easier to read.

2. **Consistency and scalability**: Tailwind CSS provides a predefined set of utility classes that follow a consistent naming convention. This ensures that your styles are applied consistently throughout your project and makes it easier to scale and maintain your codebase as it grows.

3. **Rapid development**: Tailwind CSS offers a wide range of utility classes that cover common styling needs. By using these classes, you can quickly apply styles without the need to write custom CSS or constantly switch between HTML and CSS files. This speeds up development and allows you to focus on building your application.

4. **Responsive design**: Tailwind CSS includes responsive utilities that allow you to easily create responsive layouts and adapt your styles to different screen sizes. These utilities make it convenient to handle responsiveness without cluttering your HTML with inline media queries.

5. **Optimized output**: Tailwind CSS uses a utility-first approach, which means that you only include the necessary CSS for the styles you use. This leads to smaller file sizes and faster load times compared to inline styles that may result in repetitive and bloated code.

6. **Community and ecosystem**: Tailwind CSS has a large and active community, which means you can find plenty of resources, tutorials, and support. It also integrates well with popular frontend frameworks like React, Vue.js, and Angular, providing additional functionality and convenience.

While inline styles can be suitable for certain scenarios, Tailwind CSS offers a more structured, efficient, and scalable way to style your applications, making it a popular choice among developers.

## Colors

Tailwind CSS provides a comprehensive set of utilities for working with colors. These utilities allow you to set text color, background color, border color, and more.

Here's a breakdown of the main color-related utilities in Tailwind CSS:

1. **Text color**: You can set the color of text using the `text-{color}` classes. For example, `text-red-500` will set the text color to a shade of red with a intensity of 500.

2. **Background color**: To set the background color of an element, you can use the `bg-{color}` classes. For instance, `bg-blue-200` will set the background color to a light blue shade.

3. **Border color**: Tailwind CSS provides border color utilities with the `border-{color}` classes. For instance, `border-green-600` will set the border color to a darker shade of green.

4. **Ring color**: The ring color utility is used to apply a color to the focus ring that appears around an element when it is focused. You can use the `ring-{color}` classes. For example, `ring-yellow-400` will set the ring color to a yellow shade.

5. **Placeholder color**: To change the color of the placeholder text inside an input field, you can use the `placeholder-{color}` classes. For example, `placeholder-gray-400` will set the placeholder text color to a gray shade.

6. **Gradient colors**: Tailwind CSS also provides utilities for working with gradients. You can use the `bg-gradient-{direction}-{color1}-{color2}` classes to apply linear gradients. For example, `bg-gradient-to-r from-blue-500 to-green-500` will create a horizontal gradient from blue to green.

[tailwind-customizing-colors](https://tailwindcss.com/docs/customizing-colors)

## Backgrounds

1. **Background color**: To set the background color of an element, you can use the `bg-{color}` classes. For example, `bg-blue-500` will set the background color to a shade of blue with an intensity of 500. You can replace `{color}` with various color names or use hexadecimal color codes like `bg-[#FF0000]` for red.

Example:

```html
<div className="bg-blue-500">This div has a blue background color.</div>
```

2. **Background image**: To set a background image for an element, you can use the `bg-{image}` classes. Replace `{image}` with the name of the image you want to use. By default, Tailwind CSS includes a few background images like `bg-gradient-to-r`, `bg-gradient-to-b`, and `bg-gradient-to-br`. You can also define your own background images using custom CSS.

Example:

```html
<div className="bg-gradient-to-r from-red-500 to-yellow-500">
  This div has a horizontal gradient background.
</div>
```

To add an image as a background using Tailwind CSS in a React.js project, you can follow these steps:

Step 1: Prepare the image
Make sure you have the image you want to use as the background in your project directory. You can either place it in the `public` folder or import it into your React component.

Here's an example:

```javascript
import React from 'react';
import backgroundImage from './path/to/image.jpg';

const BackgroundExample = () => {
  return (
    <div className="bg-[url] h-screen flex justify-center items-center">
      <h1 className="text-4xl font-bold text-white">Background Example</h1>
    </div>
  );
};

export default BackgroundExample;
```

Replace `[url]` with the URL or path to your image. If the image is in the `public` folder, you can use a relative path like `"bg-[./path/to/image.jpg]"`. If it's imported into your component, you can use a variable like `"bg-[${backgroundImage}]"` or require the image like `"bg-[require('./path/to/image.jpg')]"`.

```javascript
import React from 'react';
import backgroundImage from './path/to/image.jpg';

const BackgroundExample = () => {
  return (
    <div className="bg-[url] bg-cover bg-top h-screen flex justify-center items-center">
      <h1 className="text-4xl font-bold text-white">Background Example</h1>
    </div>
  );
};

export default BackgroundExample;
```

example 1

```javascript
<>
  <div className="flex justify-center items-center h-screen">
    <div
      className="bg-cover bg-center h-80 w-96"
      style={{
        backgroundImage:
          "url('https://images.pexels.com/photos/16902643/pexels-photo-16902643/free-photo-of-food-wood-landscape-mountains.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1')",
      }}
    ></div>
  </div>
</>
```

example - 2

```javascript
const App = () => {
  return (
    <div className="container mx-auto bg-red-950 p-6 h-screen">
      <h1 className="bg-red-600 font-oswald p-6">hello world, hi are u</h1>
      <div className="bg-[url('./assets/images/bg-1.jpg')] w-full h-full bg-center bg-cover bg-no-repeat  bg-red-100"></div>
    </div>
  );
};
```

example 3

- add background image using tailwind-config file.

```javascript
extend: {
      backgroundImage: {
        nature: 'url("./src/assets/images/bg-1.jpg")',
      },
    },

--------
<div className="bg-nature w-60 h-60 bg-cover bg-center bg-fixed"></div>
```

3. **Background position**: To control the position of a background image, you can use the `bg-{position}` classes. Replace `{position}` with values like `bottom`, `center`, `left`, `right`, or `top`. You can also combine multiple position values to achieve more precise positioning.

Example:

```html
<div className="bg-center">This div has a background image centered.</div>
```

4. **Background size**: To control the size of a background image, you can use the `bg-{size}` classes. Replace `{size}` with values like `auto`, `cover`, `contain`, or specific dimensions such as `w-32` or `h-48`.

Example:

```html
<div className="bg-contain">
  This div has a background image contained within its boundaries.
</div>
```

5. **Background repeat**: To specify whether a background image should repeat or not, you can use the `bg-{repeat}` classes. Replace `{repeat}` with values like `repeat`, `no-repeat`, `repeat-x`, or `repeat-y`.

Example:

```html
<div className="bg-repeat-x">
  This div has a background image repeated horizontally.
</div>
```

6. **Background attachment**: To control whether a background image should scroll with the content or stay fixed, you can use the `bg-{attachment}` classes. Replace `{attachment}` with values like `fixed`, `local`, or `scroll`.

Example:

```html
<div className="bg-fixed">
  This div has a background image fixed in the viewport.
</div>
```

[Background-image](https://tailwindcss.com/docs/background-image)

## Borders

1. **Border width**: To set the width of a border, you can use the `border-{width}` classes. Replace `{width}` with values like `0` (no border), `2` (2 pixels), `4` (4 pixels), or `8` (8 pixels). You can also use fractions like `1/2` or `1/4` to specify fractional widths.

Example:

```html
<div className="border-2">This div has a border with a width of 2 pixels.</div>
```

2. **Border color**: To set the color of a border, you can use the `border-{color}` classes. Replace `{color}` with various color names or use hexadecimal color codes like `border-#FF0000` for red.

Example:

```html
<div className="border-red-500">This div has a border with a red color.</div>
```

3. **Border style**: To specify the style of a border, you can use the `border-{style}` classes. Replace `{style}` with values like `solid`, `dashed`, `dotted`, or `none`.

Example:

```html
<div className="border-dashed">This div has a dashed border.</div>
```

4. **Rounded corners**: To create rounded corners on an element, you can use the `rounded-{size}` classes. Replace `{size}` with values like `sm` (small), `md` (medium), or `lg` (large). You can also use specific values like `rounded-2xl` or `rounded-full` for different levels of rounding.

Example:

```html
<div className="rounded-lg">This div has rounded corners.</div>
```

5. **Border radius**: To specify individual border radii for each corner of an element, you can use the `rounded-{corner}-{size}` classes. Replace `{corner}` with values like `t` (top), `b` (bottom), `l` (left), or `r` (right), and `{size}` with values like `sm`, `md`, or `lg`.

Example:

```html
<div className="rounded-t-lg rounded-b-sm">
  This div has different border radii for its top and bottom corners.
</div>
```

6. **Border opacity**: To control the opacity of a border, you can use the `border-opacity-{value}` classes. Replace `{value}` with values like `0` (transparent) to `100` (fully opaque).

Example:

```html
<div className="border-4 border-opacity-50">
  This div has a semi-transparent border.
</div>
```

[Tailwind-css-border-properties](https://tailwindcss.com/docs/border-radius)

## Typography

This will create a `tailwind.config.js` file in your project directory.

Configure Tailwind CSS
Open the `tailwind.config.js` file and locate the `theme` section. This is where you can customize various aspects of Tailwind CSS, including typography.

For example, to change the default font family, you can modify the `theme` section as follows:

```javascript
// tailwind.config.js

module.exports = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Roboto', 'Arial', 'sans-serif'],
      },
    },
  },
  // ...rest of the configuration
};
```

In this example, we've added `Roboto` as the primary font family, followed by `Arial` and the generic `sans-serif` fallback.

You can also configure other typography-related properties, such as font size, font weight, line height, and letter spacing, within the `theme` section.

Style typography elements
Now you can start using Tailwind CSS utility classes to style typography elements in your React.js components. Open the desired component file (e.g., `src/App.js`) and modify it as needed.

Here's an example of how you can style heading and paragraph elements using Tailwind CSS utility classes:

```jsx
// src/App.js

import React from 'react';

function App() {
  return (
    <div className="container mx-auto p-4">
      <h1 className="text-3xl font-bold mb-4">Welcome to My Website</h1>
      <p className="text-lg text-gray-700">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam
        tincidunt felis sit amet felis sollicitudin, ac cursus magna varius.
      </p>
    </div>
  );
}

export default App;
```

In this example, we've used classes like `text-3xl` to set the heading to an extra-large font size, `font-bold` to apply a bold font weight, and `text-lg` to set the paragraph text to a large font size. Additionally, we've used the `text-gray-700` class to apply a specific shade of gray to the paragraph text.

# spacing

1. Margin (m-):
   Use the `m-{size}` classes to apply margin to an element. Replace `{size}` with values such as `0`, `4`, `8`, `12`, `16`, `auto`, `px`, `rem`, etc. You can also specify different margin values for each side using directional classes like `m-{side}-{size}`. For example:

```jsx
<div className="m-4">{/* Content */}</div>
```

2. Padding (p-):
   Use the `p-{size}` classes to apply padding to an element. Replace `{size}` with values similar to the previous example. You can also use directional classes for different sides. For example:

```jsx
<div className="p-4">{/* Content */}</div>
```

3. Negative margin (m-):
   You can use negative margin classes to create overlapping or spacing effects. For example:

```jsx
<div className="-m-2">{/* Content */}</div>
```

4. Spacing utilities:
   Tailwind CSS provides additional spacing utility classes to control specific aspects of spacing. Some commonly used ones include:

- `mx-auto`: Centers an element horizontally by setting left and right margins to "auto".
- `my-auto`: Centers an element vertically by setting top and bottom margins to "auto".
- `space-x-{size}`: Adds horizontal spacing between child elements. Replace `{size}` with values similar to previous examples.
- `space-y-{size}`: Adds vertical spacing between child elements.

Step 5: Use spacing utility classes in your components
Open the desired component file (e.g., `src/App.js`) and modify it to include spacing utility classes where needed. For example:

```jsx
import React from 'react';

function App() {
  return (
    <div className="m-4 p-8">
      <h1 className="text-2xl mb-4">Welcome to My App</h1>
      <p className="mb-2">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      </p>
      <button className="px-4 py-2 bg-blue-500 text-white rounded">
        Click Me
      </button>
    </div>
  );
}

export default App;
```

In this example, we've added margin (`m-4`) and padding (`p-8`) to the main container. The heading has a

bottom margin (`mb-4`), the paragraph has a bottom margin (`mb-2`), and the button has horizontal and vertical padding (`px-4 py-2`).

# Sizing

1. Width and Height:
   Use the `w-{size}` and `h-{size}` classes to set the width and height of an element, respectively. Replace `{size}` with values such as `full`, `1/2`, `4`, `8`, `px`, `rem`, etc. For example:

```jsx
import React from 'react';

function App() {
  return <div className="w-full h-64 bg-gray-200">{/* Content */}</div>;
}

export default App;
```

In this example, we've set the width to full (`w-full`) and the height to 64 pixels (`h-64`) for the container.

2. Padding and Margin:
   Use the `p-{size}` and `m-{size}` classes to set padding and margin, respectively. Replace `{size}` with values similar to the previous example. You can also use directional classes for different sides. For example:

```jsx
import React from 'react';

function App() {
  return <div className="p-4 m-2 bg-gray-200">{/* Content */}</div>;
}

export default App;
```

In this example, we've added padding (`p-4`) and margin (`m-2`) to the container.

3. Min and Max Width/Height:
   Use the `min-w-{size}`, `max-w-{size}`, `min-h-{size}`, and `max-h-{size}` classes to set the minimum and maximum width and height of an element. Replace `{size}` with values similar to the previous examples. For example:

```jsx
import React from 'react';

function App() {
  return (
    <div className="min-w-0 max-w-lg min-h-screen max-h-64 bg-gray-200">
      {/* Content */}
    </div>
  );
}

export default App;
```

In this example, we've set the minimum width to 0 (`min-w-0`), the maximum width to large (`max-w-lg`), the minimum height to the screen height (`min-h-screen`), and the maximum height to 64 pixels (`max-h-64`) for the container.

# flex

Step 1: Create a Flexbox Component
Now, you can create a new React component that uses flexbox layouts with Tailwind CSS. For example, create a new file called `FlexboxComponent.js` in your `src` folder and add the following code:

```javascript
import React from 'react';

const FlexboxComponent = () => {
  return (
    <div className="flex justify-center items-center h-screen">
      <div className="flex flex-col items-center">
        <h1 className="text-4xl mb-4">Flexbox Example</h1>
        <div className="flex">
          <div className="flex-1 bg-red-500 p-4">Item 1</div>
          <div className="flex-1 bg-blue-500 p-4">Item 2</div>
          <div className="flex-1 bg-green-500 p-4">Item 3</div>
        </div>
      </div>
    </div>
  );
};

export default FlexboxComponent;
```

In this example, we have a parent container with the class `flex justify-center items-center h-screen`, which makes the content centered both horizontally and vertically on the screen. Inside the parent container, we have a flex container with the class `flex`, and three flex items with different colors and content.

Step-2: Use the Flexbox Component
Finally, you can use the `FlexboxComponent` in your main `App.js` file or any other component. For example, in `App.js`, add the following code:

```javascript
import React from 'react';
import FlexboxComponent from './FlexboxComponent';

const App = () => {
  return (
    <div>
      <FlexboxComponent />
    </div>
  );
};

export default App;
```

This will render the `FlexboxComponent` inside the `App` component.

# Grid

Step 1: Create a grid layout component
Create a new file called `Grid.js` in the `src` folder. Add the following code to create a basic grid layout:

```jsx
import React from 'react';

const Grid = () => {
  return (
    <div className="grid grid-cols-3 gap-4">
      <div className="bg-blue-500 p-4">Item 1</div>
      <div className="bg-green-500 p-4">Item 2</div>
      <div className="bg-red-500 p-4">Item 3</div>
      <div className="bg-yellow-500 p-4">Item 4</div>
      <div className="bg-purple-500 p-4">Item 5</div>
      <div className="bg-pink-500 p-4">Item 6</div>
    </div>
  );
};

export default Grid;
```

In this example, we create a grid with three columns and a gap of 4 units between each item. Each item has a different background color and padding.

Step 2 - Use the grid component
Open the `App.js` file in the `src` folder and replace its contents with the following code:

```jsx
import React from 'react';
import Grid from './Grid';

const App = () => {
  return (
    <div className="container mx-auto p-4">
      <Grid />
    </div>
  );
};

export default App;
```

In this code, we import the `Grid` component and render it within a container div.

# Layouts

## Aspect Ratio

- Utilities for controlling the aspect ratio of an element.

Step : Create a video component with aspect ratio container
In your `src` directory, create a new file called `Video.js` and add the following code:

```jsx
import React from 'react';

const Video = ({ src, aspectRatio }) => {
  return (
    <div className={`relative w-full ${aspectRatio}`}>
      <iframe
        className="absolute top-0 left-0 w-full h-full"
        src={src}
        title="Video"
        frameBorder="0"
        allowFullScreen
      ></iframe>
    </div>
  );
};

export default Video;
```

Step 7: Use the video component
In your `App.js` file, import the `Video` component and use it in your application. Replace the default content in the `App` component with the following code:

```jsx
import React from 'react';
import Video from './Video';

const App = () => {
  return (
    <div className="container mx-auto px-4">
      <h1 className="text-4xl font-bold text-center mt-8">Welcome to My App</h1>
      <Video
        src="https://www.youtube.com/embed/dQw4w9WgXcQ"
        aspectRatio="aspect-widescreen"
      />
    </div>
  );
};

export default App;
```

## Container

A component for fixing an element's width to the current breakpoint.

import React from 'react';
```javascript

const App = () => {
  return (
    <div className="container mx-auto">
      <h1 className="text-4xl font-bold text-center mt-8">Welcome to My App</h1>
      <p className="text-center mt-4">This is a container in Tailwind CSS with React.</p>
    </div>
  );
};

export default App;
```


## Object Fit

Utilities for controlling how a replaced element's content should be resized.

object-contain //	object-fit: contain;


## Object Position

Utilities for controlling how a replaced element's content should be positioned within its container.

object-bottom	 // object-position: bottom;
object-center	// object-position: center;
object-left	// object-position: left;

## Position

Utilities for controlling how an element is positioned in the DOM.

static, fixed, absolute, relative, sticky.

top-0,
left-0,

## Z-Index

Utilities for controlling the stack order of an element.

# Effects

## Box Shadow