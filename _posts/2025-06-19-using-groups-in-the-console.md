---
title: "Using groups in the console"
date: 2025-06-15T22:53:00+01:00
description: "The console.group() feature can help you diagnose issues in your web apps when you are using loops"
categories:
  - coding
tags:
  - devtools
---

Ah yes, `console.log()` - we use it more than we should, but it's just so handy! But could we use it better when debugging loops in our code?

Let's give ourselves a trivial example

```javascript
for (let i = 0; i < 3; i++) {
  for (let j = 10; j <= 15; j++) {
    console.log(String.fromCharCode(65 + i), String.fromCharCode(65 + j));
  }
}
```

If we were debugging this we could add a quick `console.log()`:

```javascript
for (let i = 0; i < 3; i++) {
  for (let j = 10; j <= 15; j++) {
    console.log(i, j);
    console.log(i, String.fromCharCode(65 + i), String.fromCharCode(65 + j));
  }
}
```

But now look at this mess!

![My Test Screenshot](/assets/posts/using-groups-in-the-console/messy.png)

We can clean this up a bit with [`console.group()`](https://developer.mozilla.org/en-US/docs/Web/API/console/group_static]).

```javascript
for (let i = 0; i < 3; i++) {
  console.group();
  for (let j = 10; j <= 15; j++) {
    console.log(i, j);
    console.log(String.fromCharCode(65 + i), String.fromCharCode(65 + j));
  }
  console.groupEnd();
}
```

![My Test Screenshot](/assets/posts/using-groups-in-the-console/groups.png)

Note that a group has to be paired, any `group()` should have a `groupEnd()` or things will get weird!

Now we can see some summaries, and even collapse groups that we're not interested in. 'console.group' isn't a helpful label, so you can provide an alternative that gives an indicator of state in this interaction of the loop.

```javascript
for (let i = 0; i < 3; i++) {
  console.group('i is ' + i); // <<< Show something more interesting that console.group
  for (let j = 10; j <= 15; j++) {
    console.log(j);
    console.log(String.fromCharCode(65 + i), String.fromCharCode(65 + j));
  }
  console.groupEnd();
}
```

![My Test Screenshot](/assets/posts/using-groups-in-the-console/labels.png)

It's easier to diagnose any issues now. But wait! The powers of `console.group()` don't end there. You can nest groups!

```javascript
for (let i = 0; i < 3; i++) {
  // Collapse the parent groups by default
  console.groupCollapsed('i is ' + i);
  for (let j = 10; j <= 15; j++) {
    console.group('j is ' + j);
    console.log(String.fromCharCode(65 + i), String.fromCharCode(65 + j));
    console.groupEnd();
  }
  console.groupEnd();
}
```

![My Test Screenshot](/assets/posts/using-groups-in-the-console/nested.png)

See that with [`console.groupCollapsed()`](https://developer.mozilla.org/en-US/docs/Web/API/console/group_static]) you can have the groups start collapsed instead of expanded, which is the default.

Next time you find your loops are driving you loopy and the console is running to hundreds of lines, consider the group functions!

[^1]: Unless you know your character codes really well!
