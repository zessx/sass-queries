# SassQueries
![SassQueries](sass-queries.png)
Manage media-queries in Sass easily.

## Configuration
Put `sass-queries.scss` file in your project, and include it via your Sass manifest:

    @import "helpers/sass-queries";

You can fully configurate SassQueries thanks to a bunch of variables prefixed with `$sq-`.  
SassQueries provides default values for these variable, so you just have to put the one you need in your `variables.scss` file:

    // Set your mobile-first breakpoints: label / min-width
    $sq-breakpoints: (
        mobile:    320px,
        tablet:    768px,
        desktop:   992px,
        wide:      1200px
    );
    // What is the media type?
    $sq-media: "all";
    // Enable (or not) a small tag displaying your current breakpoint
    $sq-debug: false;
    
## Usage
SassQueries comes with a unique mixin: `media()`, which allows you to target a starting/ending breakpoint, to specify a media type, and even to add custom options.

> Keep in mind everything works in a mobile-first way. 

    .selector {
      @media($from: tablet) {
        // starting breakpoint
      }
      @media($until: desktop) {
        // ending breakpoint
      }
      @media($from: desktop, $media: tv) {
        // media type specified
      }
      @media($until: tablet, $and: "(orientation: landscape)") {
        // additional option
      }
      @media($from: tablet, $until: desktop) {
        // starting + ending breakpoint
      }
    }
