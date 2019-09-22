# Svelte tutorial notes

## I restructured example 2.16

At around 2.16, I decided to have *App.svelte* input the data for *ContactCard.svelte*, but I had *ContactCard.svelte* display the results.  The tutorial displays the data in *App.svelte.*  I'm trying to find a pattern that seems to encapsulate data and  data displays in components.  Even letting *App.svelte* input data strikes me as somehow wrong, but I wanted to see how it works.

## At the end of Section 2

I like that *svelte* logic can affect CSS:

These two examples do the same thing:

    <div class="{userImageURL ? 'thumb' : 'thumb thumb-placeholder'}">

    <div class="thumb" : class:thumb-placeholder="{!userImageURL}">

But I don't like the second syntax very much.  Notice the colon in the second example: that's a *svelte* command.

The official version can be downloaded from [here](https://www.udemy.com/sveltejs-the-complete-guide/learn/lecture/14689512#overview).
