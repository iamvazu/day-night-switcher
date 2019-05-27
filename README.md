# Use day and night theme on your website

Reading a website at night with a clear theme is tiring for the eyes.

A good idea is then to have a clear version and a dark version of the site,
one for the day, the other for the night.

This little lib deal with that.

Before continue, you can see a live example on Codepen: <https://codepen.io/malenki/pen/MdXRbv>

## Prerequisites


### CSS

In your HTML, add into `HEAD` followings:

```html
&lt;link rel="alternate stylesheet" data-daynight-css="night" type="text/css" href="night.css"&gt;
&lt;link rel="stylesheet" data-daynight-css="day" type="text/css" href="day.css"&gt;
```

The important part is to use attribute `data-daynight-css` on CSS used for night and day times.

At load time, the disabled theme must have attribute `rel="alternate stylesheet"`, enabled theme must have attribute `rel="stylesheet"`.

Note: more than one CSS per moment is possible, just do not forget the `data-nightday-css` attribute.

### Swither(s)

To switch from day to night or night to day, you must define at least one switcher, for example using a link:

```html
&lt;a data-daynight-moment="day" href="#foo"&gt;Switch to night theme&lt;/a&gt;
```

Note that attribute `data-daynight-moment` must have actual desired moment.

## Add script

Add script at bottom of the `BODY` tag:

```html
&lt;script src="/path/to/daynight.min.js"&gt;&lt;/script&gt;
```

And that’s all, no more work to enable this feature!

Note: you can download the script from Github, or you can get it using NPM:

```bash
npm i day-night-switcher
```

## Styling switcher

As switcher uses specific attribute, you may define some style to change it and show its status.

An example could be:

```css
    a[data-daynight-moment] {
        text-decoration: none;
        transition: all 200ms;
    }
    a[data-daynight-moment*="night"]:before {
        content: "🌙";
    }

    a[data-daynight-moment*="day"]:before {
        content: "☀️";
    }
```


