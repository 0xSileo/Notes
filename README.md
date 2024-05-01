# Notes
Notes on all kinds of topics. Learning in public is cool.

## Notetaking

### Structure

This has yet to be perfected, I love the idea of adding labels to stuff, so that it can fit in mutliple categories but choosing a good set of labels is a challenge by itself. For now, I will be creating categories that I consider good enough. I'll try applying a library-like structure.

### Technique

Not sure yet, notes will live on the git repostory for now, but I am probably going to use `pandoc` to convert to html, and maybe even pdf. I have had good results with this command, particularly for math notation : 

```bash
pandoc --toc --standalone --mathjax -f markdown -t html test.md -o test.html
```

with the following options : 

- `--toc`: Generate a table of contents.
- `--standalone`: Produce a standalone HTML file.
- `--mathjax`: Enable MathJax support for rendering equations.
- `-f markdown`: Specify input format as Markdown.
- `-t html`: Specify output format as HTML.
