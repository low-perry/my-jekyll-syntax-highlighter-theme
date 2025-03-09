# Jekyll syntax highlighter theme

This repository has custom themes for code syntax highlighter in markdown files. It supports both light and dark mode:

*Dark Mode*:

![Dark Mode](/assets/dark-mode-syntax.png)

*Light Mode*:

![Light Mode](/assets/light-mode-syntax.png)

## To Enable Syntax Highlighting

### **Step 1: Install the Rouge Gem**

Ensure you're in your project directory by running the following command in your terminal:

`cd your_project`

Then, install the Rouge gem:

`gem install rouge`.


### **Step 2: Update** `_config.yml`

Modify your `_config.yml` file to include the following settings:

```yaml

    # Markdown settings

    markdown: kramdown
    highlighter: rouge
    kramdown:
    input: GFM

```

### **Step 3: Add a Syntax Stylesheet**

In your `assets/css` directory create a new css file named `syntax.css`. Link this file in your main layout (`_layouts/default.html` or equivalent) by adding:

```html

    <link rel="stylesheet" href="{{ '/assets/css/syntax.css' | relative_url }}">

```

### **Step 4. Choose a syntax Theme**

To style your code, select a Rouge theme:

1. Visit [this GitHub repository](https://github.com/low-perry/my-jekyll-syntax-highlighter-theme) .

2. Copy the content of your preferred theme into `syntax.css` file.
