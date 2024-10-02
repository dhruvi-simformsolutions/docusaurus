# Adding CSS to MDX in Docusaurus

## 1. Inline CSS

You can use inline styles directly in your MDX:

```mdx
# My Styled Heading

<div style={{ color: "blue", fontSize: "20px" }}>
  This text is blue and larger.
</div>
```

## 2. CSS Modules

First, create a CSS module file, e.g., `styles.module.css`:

```css
.myCustomClass {
  color: green;
  font-weight: bold;
}
```

Then, in your MDX file:

```mdx
import styles from "./styles.module.css";

# My Styled Content

<div className={styles.myCustomClass}>This text uses the CSS module style.</div>
```

## 3. Global CSS

Create a global CSS file, e.g., `custom.css`:

```css
.globalStyle {
  background-color: #f0f0f0;
  padding: 10px;
}
```

Import it in your `docusaurus.config.js`:

```javascript
module.exports = {
  // ...other config
  stylesheets: ["/css/custom.css"],
};
```

Use it in your MDX:

```mdx
# Global Styled Content

<div className="globalStyle">This div uses a global style.</div>
```

## 4. CSS-in-JS

If you're using a CSS-in-JS library like styled-components:

```mdx
import styled from "styled-components";

const StyledDiv = styled.div`  color: purple;
  font-size: 16px;`;

# Styled Components Example

<StyledDiv>This text is styled using styled-components.</StyledDiv>
```

Remember to install and configure any necessary plugins for CSS-in-JS libraries.
