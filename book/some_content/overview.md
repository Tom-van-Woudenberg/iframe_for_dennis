# Wishes

I want to be able to add iframes using syntax:

````
```{iframe} http-link
:remove_background: true
:dynamic height: true
```
````

Where `:remove_background` removes a white background in light mode (in dark mode it's removed by sphinx-image-inverter). My script was:
```
<style> 
    @media (prefers-color-scheme: light) {
        iframe[src*="tudelft.h5p.com"] {
            filter: invert(1); 
            background: transparent; 
            mix-blend-mode: difference;
        }
    }
</style>
```

Dynamic height is to make sure that the iframe's height is adapted to the size of the content. H5p provides a script for it:
`<script src="https://tudelft.h5p.com/js/h5p-resizer.js" charset="UTF-8"></script>`

These iframes must be able to next within other stuff, like:

```{exercise}
<iframe src="https://tudelft.h5p.com/content/1292011179114024347/embed" aria-label="Importing libraries" width="1088" height="637" frameborder="0" allowfullscreen="allowfullscreen" allow="autoplay *; geolocation *; microphone *; camera *; midi *; encrypted-media *"></iframe><script src="https://tudelft.h5p.com/js/h5p-resizer.js" charset="UTF-8"></script>
<style> 
    @media (prefers-color-scheme: light) {
        iframe[src*="tudelft.h5p.com"] {
            filter: invert(1); 
            background: transparent; 
            mix-blend-mode: difference;
        }
    }
</style>
```