# Atom w/ Transparency

This has only been adjusted and tested for Mac OS X.

## Building

```bash
./script/build-transparency;
```

The binary will be compiled to `./dist/Atom.app`.

## Stylesheet

Add the following CSS to your Atom theme.

Settings > Themes > Your Stylesheet

```css
html {
  background: rgba(0, 0, 0, 0.75);
  padding-top: 28px;
}

atom-text-editor,
.footer,
.footer .status-bar,
.line-numbers,
.line-numbers > div,
.tab-bar,
.tab-bar .tab.active,
.tab-bar .tab .title,
.workspace {
  background-color: transparent !important;
}

atom-text-editor::shadow .gutter {
  background-color: rgba(0, 0, 0, 0.25);
  border-right: 1px solid rgba(255, 255, 255, 0.25);
  color: #555;
  margin-right: 15px;

  .line-number {
    opacity: 1 !important;

    &.cursor-line,
    &:hover {
      color: #fff;
    }
  }
}

.footer {
  border-top: 1px solid #555;
}

head {
  display: block;
}

title {
  -webkit-user-select: none;
  color: #888;
  display: block;
  position: absolute;
  text-align: center;
  top: 10px;
  width: 100%;
}

html.focus title {
  color: #ccc;
}

.titlebar-avatar {
  border-radius: 24px;
  display: block !important;
  height: 24px;
  position: absolute;
  right: 5px;
  top: 5px;
  width: 24px;
}
```
