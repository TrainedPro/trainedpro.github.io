### Styling Text
- **Syntax:**  
  - Bold: `**text**`  
  - Italic: `*text*`  
  - Strikethrough: `~~text~~`  
  - Sub/Superscript: `<sub>text</sub>`, `<sup>text</sup>`
- **Parameters:** None  
- **Example:**
  ```markdown
  **bold text**

### Blockquotes
- **Syntax:**  
  - Start with `>`; supports HTML `<br>` and citations.
- **Parameters:**  
  - `Citation reference` (optional).  
- **Example:**
  ```markdown
  > Quote text<br>
  > — Citation
  ```

### Alerts
- **Syntax:**  
  - Use extended blockquotes with alert types like `[!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]`, `[!CAUTION]`.
- **Parameters:** None  
- **Example:**
  ```markdown
  > [!NOTE]
  > Note message.
  ```

### Tables
- **Syntax:**  
  - Use pipes (`|`) and dashes (`-`) to define headers and rows.
- **Parameters:**  
  - `Header row` (required).  
- **Example:**
  ```markdown
  | Name | Age |
  | Bob  | 27  |
  ```

### Lists
- **Ordered Lists:**  
  - **Syntax:** Numbers followed by a period.  
  - **Example:**
    ```markdown
    1. First
    2. Second
    ```
- **Unordered Lists:**  
  - **Syntax:** Use `*` (or `-`).  
  - **Example:**
    ```markdown
    * Item one
    * Item two
    ```
- **Nested Lists:**  
  - **Syntax:** Indent nested items with spaces.  
  - **Example:**
    ```markdown
    * Fruit
      * Apple
      * Banana
    ```

### Images
- **Syntax:**  
  - `![alt text](image_url "optional caption")`
- **Parameters:**  
  - `image URL` (required)  
  - `Alt text` (optional)  
  - `Caption` (optional)  
- **Example:**
  ```markdown
  ![landscape](https://picsum.photos/800/600 "Caption")
  ```

### Syntax Highlighting
- **Syntax:**  
  - Use triple backticks with a language identifier, appending parameters in curly braces.
- **Parameters:**  
  - `filename` (optional): Display a file name or title.  
  - `base_url` (optional): Combine with `filename` to create a link.  
  - `linenos` (optional): Enable line numbering (e.g., `table`).  
  - `linenostart` (optional): Set the starting line number.  
  - `hl_lines` (optional): Highlight specific lines (as a list).  
- **Example:**
  ```python {linenos=table,linenostart=42,hl_lines=[2,4],filename="hello.py"}
  def say_hello():
      print("Hello!")

  def main():
      say_hello()
  ```

### Callout Component
- **Syntax:**  
  - `{{< callout [parameters] >}} Content {{< /callout >}}`
- **Parameters:**  
  - `emoji` (optional): Sets an icon (e.g., `"🌐"`).  
  - `type` (optional): Specifies style; accepts `"info"`, `"warning"`, or `"error"`.  
- **Example:**
  ```markdown
  {{< callout emoji="🌐" >}}
    Hugo can be used to create various types of websites.
  {{< /callout >}}

  {{< callout type="info" >}}
    Visit GitHub for the latest releases.
  {{< /callout >}}
  ```

### Cards Component
- **Syntax:**  
  - Cards container: `{{< cards [cols="N"] >}} ... {{< /cards >}}`  
  - Card: `{{< card [parameters] >}} ... {{< /card >}}`
- **Parameters:**  
  - `link` (optional): URL for the card.  
  - `title` (required): Card title.  
  - `subtitle` (optional): Subtitle (supports Markdown).  
  - `icon` (optional): Icon name.  
  - `tag` (optional): Tag text.  
  - `tagColor`/`tagType` (optional): Tag style (default: gray; alternatives: yellow, red, blue, or semantic types like error, info, warning).  
  - `image` (optional): Image URL (for image cards).  
  - `method` (optional): Hugo image processing method (e.g., Resize, Fit, Fill, Crop).  
  - `options` (optional): Image processing options.  
  - `cols` (optional): Maximum number of columns in the cards container.  
- **Example:**
  ```markdown
  {{< cards cols="2" >}}
    {{< card link="/" title="Image Card" image="https://example.com/image.jpg" subtitle="Subtitle" tag="New" tagType="info" >}}
    {{< card link="/about" title="Simple Card" icon="info" >}}
  {{< /cards >}}
  ```

### Details Component
- **Syntax:**  
  - `{{% details title="Your Title" [closed="true"] %}} Content {{% /details %}}`
- **Parameters:**  
  - `title` (required): Header for the collapsible section.  
  - `closed` (optional): Set to `"true"` to hide content by default.  
- **Example:**
  ```markdown
  {{% details title="Details" %}}
  This is the content with **Markdown** support.
  {{% /details %}}

  {{% details title="Click me to reveal" closed="true" %}}
  This content is hidden by default.
  {{% /details %}}
  ```

### FileTree Component
- **Syntax:**  
  - Container: `{{< filetree/container >}} ... {{< /filetree/container >}}`  
  - Folder: `{{< filetree/folder name="folderName" [state="closed"] >}} ... {{< /filetree/folder >}}`  
  - File: `{{< filetree/file name="filename" >}}`
- **Parameters:**  
  - `name` (required): Name of the folder or file.  
  - `state` (optional): e.g., `"closed"` to collapse the folder.  
- **Example:**
  ```markdown
  {{< filetree/container >}}
    {{< filetree/folder name="content" >}}
      {{< filetree/file name="_index.md" >}}
      {{< filetree/folder name="docs" state="closed" >}}
        {{< filetree/file name="_index.md" >}}
        {{< filetree/file name="introduction.md" >}}
        {{< filetree/file name="introduction.fr.md" >}}
      {{< /filetree/folder >}}
    {{< /filetree/folder >}}
    {{< filetree/file name="hugo.toml" >}}
  {{< /filetree/container >}}
  ```

### Icon Component
- **Syntax:**  
  - Inline shortcode: `{{< icon "iconName" >}}`
- **Parameters:**  
  - `"iconName"` (required): Name of the icon to display.  
- **Additional Note:**  
  - Ensure inline shortcodes are enabled in your config (`enableInlineShortcodes: true`).  
- **Example:**
  ```markdown
  {{< icon "academic-cap" >}}
  ```
- **To add custom icons:**  
  Define them in `data/icons.yaml`:
  ```yaml
  your-icon: <svg>your icon svg content</svg>
  ```
  Then use:
  ```markdown
  {{< icon "your-icon" >}}
  ```

### Steps Component
- **Syntax:**  
  - `{{% steps %}} ... {{% /steps %}}`  
  _Within the block, use Markdown H3 headers (`###`) for each step._
- **Parameters:**  
  - None; content must be Markdown.  
- **Example:**
  ```markdown
  {{% steps %}}
  ### Step 1
  This is the first step.

  ### Step 2
  This is the second step.

  ### Step 3
  This is the third step.
  {{% /steps %}}
  ```

### Tabs Component
- **Syntax:**  
  - Tabs container: `{{< tabs items="Tab1,Tab2,Tab3" [defaultIndex="N"] >}} ... {{< /tabs >}}`  
  - Tab: `{{< tab >}} Content {{< /tab >}}`
- **Parameters:**  
  - `items` (required): Comma-separated list of tab names.  
  - `defaultIndex` (optional): Index (starting at 0) of the tab selected by default.  
- **Example – Default Usage:**
  ```markdown
  {{< tabs items="JSON,YAML,TOML" >}}
    {{< tab >}}**JSON**: JavaScript Object Notation.{{< /tab >}}
    {{< tab >}}**YAML**: Human-readable data serialization.{{< /tab >}}
    {{< tab >}}**TOML**: Minimal configuration format.{{< /tab >}}
  {{< /tabs >}}
  ```
- **Example – With Default Selected:**
  ```markdown
  {{< tabs items="JSON,YAML,TOML" defaultIndex="1" >}}
    {{< tab >}}**JSON**: JavaScript Object Notation.{{< /tab >}}
    {{< tab >}}**YAML**: Human-readable data serialization.{{< /tab >}}
    {{< tab >}}**TOML**: Minimal configuration format.{{< /tab >}}
  {{< /tabs >}}
  ```
- **Markdown Support Example:**
  ```markdown
  {{< tabs items="JSON,YAML,TOML" >}}
    {{< tab >}}
    ```json
    { "hello": "world" }
    ```
    {{< /tab >}}

    {{< tab >}}
    ```yaml
    hello: world
    ```
    {{< /tab >}}

    {{< tab >}}
    ```toml
    hello = "world"
    ```
    {{< /tab >}}
  {{< /tabs >}}
  ``` 