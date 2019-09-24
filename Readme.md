# Svelte tutorial notes

# Downloading and initializing a new project

## Downloading

This course has me download several versions of *project-setup.zip* and use them to replace previous projects.

Unzipping the file creates these files:

    package.json
    public/
    rollup.config.js
    src/

I add a Readme.md (this file).

## Install dependencies

The command

    $ sudo npm install

downloads a library, node_modules, and a lock file on the *package.json* file telling *npm* what to download.

    Readme.md
    node_modules/
    package-lock.json
    package.json
    public/
    rollup.config.js
    src/


## I restructured example 2.16

At around 2.16, I decided to have *App.svelte* input the data for *ContactCard.svelte*, but I had *ContactCard.svelte* display the results.  The tutorial displays the data in *App.svelte.*  I'm trying to find a pattern that seems to encapsulate data and  data displays in components.  Even letting *App.svelte* input data strikes me as somehow wrong, but I wanted to see how it works.

## At the end of Section 2

I like that *svelte* logic can affect CSS:

These two examples do the same thing:

    <div class="{userImageURL ? 'thumb' : 'thumb thumb-placeholder'}">

    <div class="thumb" : class:thumb-placeholder="{!userImageURL}">

But I don't like the second syntax very much.  Notice the colon in the second example: that's a *svelte* command.

The official version can be downloaded from [here](https://www.udemy.com/sveltejs-the-complete-guide/learn/lecture/14689512#overview).

## Creating Multiple Contact Cards (§3.27)

*App.svelte* contains an array of card data, which it loops through, creating instances of each card using *ContactCard.svelte* as a template.

## Adding Unique ID to the Contact Card instances (§3.29)

I don't fully understand this process, so be sure to review if necessary.

## Resources for §3.29

### Links to Official Docs

    * [Official Docs (if)](https://svelte.dev/tutorial/if-blocks)
    * [Official Docs (each)](https://svelte.dev/tutorial/each-blocks)
    * [Official Docs (keys)](https://svelte.dev/tutorial/keyed-each-blocks)

### Resources for this lecture

* project-setup.zip
* cond-loops-01-if.zip
* cond-loops-02-each.zip
* cond-loops-03-with-keys.zip
* cond-loops-04-more-on-keys.zip

# §4

## §4.34 Making Svelte notice changes

This is a lesson about [javascript references](https://academind.com/learn/javascript/reference-vs-primitive-values/).

## §4.35 Svelte event modifiers

This very cool ability does things such as preventing double submissions, etc. [This explanatory video](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture) makes me think that this is a javascript ability and not just svelte's.

E.g.,

    <button on:click|once={some function....>

### Forms without Action tags

This is worth rewatching when I have a form.

## §4.36 Inline functions

Max recommends having buttons call functions, and I agree, but they can be created inline.

