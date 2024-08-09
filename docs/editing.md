---
title: Editing a page
---
# Editing

## Tabs
```md title="code"
=== "tab 1"
    content of tab 1
=== "tab 2"
    content of tab 2
```
Result:
=== "tab 1"
    content of tab 1
=== "tab 2"
    content of tab 2

## Flowcharts and Diagrams
- <a href='https://squidfunk.github.io/mkdocs-material/reference/diagrams/#using-flowcharts' target='_blank'>Flowcharts</a> and many types of <a href='https://squidfunk.github.io/mkdocs-material/reference/diagrams/#using-sequence-diagrams' target='_blank'>diagrams</a>  

## Admonition
abstract, bug, danger, example, info, note, question, quote, success, tip, warning.
### Example
!!! warning "content always displayed"
    Content always displayed  
    Use "customized title" to give a title to the admonition  
    Use !!! to start an admonition

??? note "content hidden by default and need to click on the title bar to open"
    Use ??? to start an admonition

???+ danger "content displayed by default and can click  on the title bar to hide"
    Use ???+ to start an admonition

  > - Code can be inside an admonition, as the examples in `code blocks/`<a href='../codeBlocks/#code-line-numbering'>`code line numbering`</a>


## Icons
### Search for an icon
MkDocs-material <a href='https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/' target='_blank'>Search</a> for an icon

### Icons with .md
```yaml title="mkdocs.yml"
# to use mkdocs-material library of icons (md)
markdown_extensions:
  - attr_list
  - pymdownx.emoji:
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
```

### Icons with .html

```yaml title="mkdocs.yml"
extra_css:
  - https://cdn.jsdelivr.net/npm/@mdi/font@6.5.95/css/materialdesignicons.min.css
```

Differences syntax for icon in `md` and in `html`:

=== "In md :material-*:"
    The icon :material-flask-outline: is achieved in .md
    ```md
    The icon :material-flask-outline: is achieved in .md
    ```

=== "In html i class ='mdi mdi-*'"
    The icon <i class="mdi mdi-flask-outline"></i> is achieved in .html
    ```html
    The icon <i class="mdi mdi-flask-outline"></i> is achieved in .html
    ```
### Examples
<a href='./assets/sampleHamk.zip' download>
  <i class="mdi mdi-folder-download"></i>
</a> `html mdi mdi-folder-download`/
[:material-folder-download:](./assets/sampleHamk.zip) `md :material-folder-download:`  
Similarly  
<a href='./assets/sampleHamk.zip' download>
  <i class='fa-solid fa-file-arrow-down'></i>
</a> `html` / [:fontawesome-solid-file-arrow-down:](./assets/sampleHamk.zip) `md`  
<a href='./assets/sampleHamk.zip' download>
  <i class='fa-solid fa-download'></i>
</a> `html` / [:fontawesome-solid-download:](./assets/sampleHamk.zip) `md`  
<a href='./assets/sampleHamk.zip' download>
  <i class='fa-regular fa-floppy-disk'></i>
</a> `html` / [:fontawesome-regular-floppy-disk:](./assets/sampleHamk.zip) `md`  
<a href='./assets/sampleHamk.zip' download>
  <i class='fa-solid fa-cloud-arrow-down'></i>
</a> `html` / [:fontawesome-solid-cloud-arrow-down:](./assets/sampleHamk.zip) `md`   
Using in a button  
<a href='./assets/sampleHamk.zip' download class="md-button md-button--primary">
  <i class="mdi mdi-folder-download"></i> Download the template `.zip`
</a> `html` / 
[:material-folder-download: Download the template `.zip`](./assets/sampleHamk.zip){ .md-button .md-button--primary} `md`

## Videos  
???+ note "documentation"
    See the discussion at <a href='https://github.com/squidfunk/mkdocs-material/discussions/3984' target='_blank'>discussions/3984</a>  
### Google Drive
:material-folder-google-drive:{ .google-drive }  
```html title="In the .md file, attn to the src syntax ending 'preview' for googledrive"
<div class='video-container'> <!--(1)!-->
  <iframe src='https://drive.google.com/file/d/[FILE_ID]/preview' allowfullscreen></iframe>
</div>
```

1. /file/d/[FILE_ID]/preview

```css title="css for the video frame"
.video-container {
    position: relative; /* allows the iframe element inside it to be positioned relative to this container. */
    width: 100%; /* makes the container take up 100% of the width of its parent element */
    padding-bottom: 56.25%; /* 16:9 aspect ratio */
    height: 0; /*  height set to 0 because padding is used to define the aspect ratio of the container */
    overflow: hidden; /* ensures that the iframe content doesn't spill out of the container */
    max-width: 100%; /* ensures the container doesn't grow larger than its parent element, maintaining responsive behavior. */
    background: #000; /* placeholder color before the video loads */
}
.video-container iframe {
    position: absolute; /* sets the position of the iframe to absolute, so it will be positioned relative 
        to the nearest positioned ancestor (in this case, .video-container which is set to relative above) */
    top: 0; /* positions the top edge of the iframe at the top of the container*/
    left: 0; /* positions the left edge of the iframe at the left of the container */
    width: 100%; /* makes the iframe take up 100% of the width of the container */
    height: 100%; /* makes the iframe take up 100% of the height of the container. */
    border: 0; /* removes any default border that might be applied to the iframe */
}
```
The Working Solution, responsive: `iframe in div with css`:  
<div class='video-container'>
  <iframe src='https://drive.google.com/file/d/1uGRddSym1KbVSJit2DNoMiAGE4uakcY7/preview' allowfullscreen></iframe>
</div>

### YouTube
:fontawesome-brands-youtube:{ .youtube }

```html title="https://www.youtube.com/EMBED/videoID"
The Working Solution, responsive: `iframe in div with css`:  
<div class='video-container'> <!--(1)!-->
  <iframe src='https://www.youtube.com/embed/CF6ZGbz59gE' allowfullscreen></iframe>
</div>
```

1. add /embed/ to the code

The Working Solution, responsive: `iframe in div with css`:  
<div class='video-container'>
  <iframe src='https://www.youtube.com/embed/smbX1wHhGjs' allowfullscreen></iframe>
</div>

## Pdf
```html title="embedding pdf"
<iframe src='../assets/pdf/poster_mi24_final.pdf' width=100% height=700px>This browser does not support PDFs. Please download the PDF to view it: <a href='../assets/pdf/poster_mi24_final.pdf'>Download PDF</a>
</iframe>
```

<iframe src='../assets/pdf/poster_mi24_final.pdf' width=100% height=700px>This browser does not support PDFs. Please download the PDF to view it: <a href='../assets/pdf/poster_mi24_final.pdf'>Download PDF</a>
</iframe>