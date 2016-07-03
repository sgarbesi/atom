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

### Transparency

```css
/* Transparency */
html {
  background: rgba(0, 0, 0, 0.7);
  padding-top: 35px;
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
  margin-right: 5px;

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
  font-size: 12px;
  height: 35px;
  padding-top: 10px;
  position: absolute;
  text-align: center;
  top: 0px;
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

### TextMate Clone

Make sure to include the transparency CSS with this.

```css
/* TextMate Clone */
atom-pane {
  border: 0 !important;
}

.tab-bar {
  background: #c4c4c4 !important;
  box-shadow: inset 0 1px 0 0 #b0b0b0;
  color: #000 !important;

  .tab {
    border-left: 1px solid #b0b0b0;
    border-image: none;

    &:first-child {
      margin-left: -1px;
    }

    &:last-child {
      border-right: 1px solid #b0b0b0;
    }

    &::after {
      border: 0;
      border-bottom: 1px solid #262626;
      box-shadow: none !important;
    }

    &::before {
      background: transparent !important;
    }

    &.active {
      background-color: #d3d3d3 !important;
      border-color: #b0b0b0;
      height: 35px;
      padding-top: 1px;
      position: relative;
      top: -1px;

      &::after {
        border: 1px solid #b0b0b0 !important;
        border-top: 0;
      }

      .title {
        color: #000;
        font-weight: 600;
      }
    }

    .title {
      color: #555;
    }

    .close-icon {
      color: #000;
      top: 11px !important;
    }
  }
}

title {
  background: linear-gradient(to bottom,  rgba(246,246,246,1) 0%,rgba(211,211,211,1) 100%) !important;
  color: #000 !important;
}

.titlebar-avatar {
  right: 10px;
  top: 6px;
}

atom-text-editor::shadow {
  .indent-guide {
    box-shadow: none !important;
  }

  .line-number.foldable .icon-right {
    color: #fff;
    visibility: visible;
  }

  .gutter[gutter-name="linter"] {
    display: none;
  }
}

.horizontal {
  .left,
  .vertical atom-pane-container atom-pane {
    padding: 0 !important;
  }
}

html.blur {
  title {
    background: #f6f6f6 !important;
    color: #aaa !important;
  }

  .tab {
    .title {
      color: #888 !important;
    }

    &.active {
      background-color: #f6f6f6 !important;
    }
  }
}
```
