# CSS Grid

---

# Why grids?

---

### Designers have been using grids for a very long time

![New York Times Grid](day07/01CSSgrid/newsGrid.png)

---

# This transferred over to web design

---

### So we started it with CSS

![Bootstrap Grid](day07/01CSSgrid/bootGrid.png)

---

- Usually 12 columns
- Put classes on your sectioning elements
- Span the number of columns you specify

---

### There are loads

- Of CSS grid systems
- Included in frameworks
- Just have a google!

---

# But...

---

# CSS Grid is here

---

- Not tied into a system
- No addons needed
- No added classes

---

### Used for laying out a page

- Popping content in the right place
- It's pretty new
- It's DOM dependent

---

### How to use

```css
.page__home {
	display: grid;
}
```

---

### OK it's a bit more complicated than that

---

### Specify the amount of cols & rows

```css
.page__home {
	display: grid;
	grid-template-columns: 100px 1fr 100px;
	grid-template-rows: repeat(4, 1fr);
}
```

---

This is an explicit grid:

We specify the grid areas.

If we didn't set cols & rows the grid would do it for us and be an _implicit_ grid

---

### A couple of notes

The `fr` unit is only available for grid

(We are considering it as a global unit \o/)

There's also a minmax() function

And you can put a gap between these areas

```css
grid-template-columns: minmax(100px, 300px);
grid-gap: 1rem;
```

---

# How do we get things in places

---

We can name the areas we have created

```css
.page__home {
	display: grid;
	grid-template-columns: 100px 1fr 100px;
	grid-template-rows: repeat(4, 1fr);
	grid-template-areas:
		"header header header"
		"main main aside"
		"main main ."
		"footer footer ."
	;
}
```

---

### Then we can reference those names when we're styling the child sections

```css
.header-main {
	grid-area: header;
}
```

---

# Or

---

### We don't have to do that at all

Grids have number lines automatically

![Bootstrap Grid](day07/01CSSgrid/gridNum.png)

---

```css
.header-main {
	grid-row: 1 / 2;
	grid-column: 1 / 4;
}
```

Shorthand

```css
.header-main {
	grid-area: 1 / 1 / 2 / 4;
}
```

---

There's also a `span` keyword which I want to mention, but right now could be too confusing. I would get used to what we've just been through.

---

### Setting size on implicit grid

```css
.page__home {
	grid-auto-rows: 140px;
	grid-auto-flow: column;
}
```

---

### Aligning children

```css
/* on parent */
.page__home {
	justify-items: start;
	align-items: stretch;
}

/* on individual child */
.header-main {
	justify-self: end;
	align-self: center;
}
```
---

### Support

Polyfills: (you don't need one)

[https://www.smashingmagazine.com/2017/11/css-grid-supporting-browsers-without-grid/](https://www.smashingmagazine.com/2017/11/css-grid-supporting-browsers-without-grid/)

[https://caniuse.com/#search=grid](https://caniuse.com/#search=grid)

---

# Todays task

Mark up all the pages and lay them out with CSS grid

NO STYLING TODAY

We're using Sass tomorrow for this

Focus on HTML and grid - USE FIREFOX

---

### HELP!

[https://mozilladevelopers.github.io/playground/css-grid](https://mozilladevelopers.github.io/playground/css-grid)

[http://learncssgrid.com/](http://learncssgrid.com/)






