---
layout: post
title: "Markdown Styles Reference"
subtitle: "A comprehensive guide to all available markdown formatting for WordSen blog posts"
date: 2025-08-30
author: "WordSen Team"
permalink: /md/
---

This page demonstrates all the markdown styling available for your WordSen blog posts. Use this as a reference when writing your content.

# Header 1 (H1)
This is the largest header, typically used for main article titles. It's already used in the post title, so you'd rarely use H1 in the content itself.

## Header 2 (H2)
This is perfect for major sections in your blog posts. It creates clear visual breaks and helps organize your content.

### Header 3 (H3)
Use this for subsections under your H2 headers. Great for breaking down complex topics into digestible parts.

#### Header 4 (H4)
This is the smallest recommended header for blog content. Use it for sub-subsections when you need further organization.

## Text Formatting

Here's a paragraph of regular text to show the default styling. This demonstrates the base typography that will be used throughout your blog posts. The text is designed to be highly readable with proper line spacing and font sizing.

**Bold text** stands out and draws attention to important points.

*Italic text* adds emphasis and is great for book titles, foreign words, or subtle emphasis.

***Bold and italic combined*** for maximum emphasis when really needed.

You can also use `inline code` to highlight technical terms, file names, or short code snippets within your paragraphs.

## Lists

### Unordered Lists (Bullet Points)
- This is a bullet point
- Here's another one
- And a third item
  - You can indent for sub-items
  - Like this second sub-item
    - And even further nesting
- Back to the main level

### Ordered Lists (Numbered)
1. First item in the sequence
2. Second item follows logically
3. Third item continues the pattern
   1. Sub-items can also be numbered
   2. They maintain their own sequence
   3. Very useful for step-by-step instructions
4. Back to the main sequence

### Mixed Lists
1. You can combine different list types
2. Second numbered item
   - With bullet sub-items
   - Another bullet point
3. Back to numbers

## Quotes and Callouts

> This is a blockquote. It's perfect for highlighting important thoughts, featuring quotes from interviews, or calling attention to key insights. The styling makes it stand out from regular paragraphs while maintaining readability.

> You can have multiple paragraphs in a blockquote.
> 
> Just make sure to prefix each line with the > symbol. This is often used for testimonials, important warnings, or philosophical thoughts that deserve special attention.

## Code Examples

### Inline Code
When referring to `variables`, `function names`, or `file.txt` names within your text, use single backticks.

### Code Blocks
For larger code examples, use triple backticks:

```
This is a basic code block
You can put any code here
It maintains formatting and spacing
```

You can also specify the language for syntax highlighting:

```javascript
// JavaScript example
function greetUser(name) {
    return `Hello, ${name}! Welcome to WordSen.`;
}

const user = "Developer";
console.log(greetUser(user));
```

```python
# Python example
def calculate_words_learned(days_studied, words_per_day):
    """Calculate total words learned over time."""
    return days_studied * words_per_day

total_words = calculate_words_learned(30, 25)
print(f"In 30 days, you'll learn {total_words} words!")
```

```css
/* CSS example */
.blog-post {
    max-width: 700px;
    margin: 0 auto;
    line-height: 1.7;
    color: #2d3748;
}

.highlight {
    background: var(--accent-color);
    padding: 0.25rem 0.5rem;
    border-radius: 4px;
}
```

## Links and Navigation

Here's how different types of links look:

- [External link to Google](https://google.com)
- [Internal link to homepage]({{ '/' | relative_url }})
- [Link to Features page]({{ '/features/why-1000-words/' | relative_url }})

## Horizontal Rules

You can create visual breaks in your content with horizontal rules:

---

Like the line above. Use three dashes on their own line.

## Tables

| Feature | Description | Status |
|---------|-------------|--------|
| Flashcards | Smart spaced repetition | ✅ Available |
| Progress Tracking | Visual learning metrics | ✅ Available |
| Motivational Pet | Gamification element | 🚧 In Development |
| Social Features | Share progress with friends | 📅 Planned |

## Special Characters and Emoji

You can use emoji naturally in your markdown: 🎯 📚 ✨ 🚀

Special characters work too: © ® ™ → ← ↑ ↓

## Line Breaks and Spacing

To create a line break within a paragraph,  
add two spaces at the end of a line.

To create a new paragraph, just add a blank line between blocks of text.

## Combining Elements

You can combine different markdown elements effectively:

### Example: Feature Explanation

When learning a new language, **consistency is key**. Here's why the WordSen approach works:

1. **Spaced Repetition**: Our algorithm shows you words just before you forget them
2. **Contextual Learning**: Every word comes with real-world examples
3. **Progress Tracking**: Visual feedback keeps you motivated

> "The best time to plant a tree was 20 years ago. The second best time is now." - Chinese Proverb

This applies perfectly to language learning. Start today with these simple steps:

```markdown
# Your Daily WordSen Routine
1. Review 10 old cards
2. Learn 5 new words
3. Practice with mini-games
4. Check your progress
```

For technical questions, email us at `support@wordsen.com` or check our [FAQ page](#).

---

## Typography Scale Reference

This section shows the visual hierarchy of all headers in context:

# This is H1 - Main Title Level
## This is H2 - Major Section
### This is H3 - Subsection  
#### This is H4 - Minor Subsection

Regular paragraph text flows at this size and weight. It's optimized for comfortable reading on all devices.

---

*This reference page contains all the styling options available for your WordSen blog posts. Bookmark this page and refer to it when crafting your content!*