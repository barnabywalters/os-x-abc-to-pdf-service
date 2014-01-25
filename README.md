ABC notation to PDF Mac OS X service
=======================

An automator service for turning a text file containing ABC music notation into a PDF. Requires abcm2ps and ps2pdf.

## Installation

1. Build and install abcm2ps and ps2pdf, e.g. `brew install abcm2ps ghostscript` using [Homebrew](http://brew.sh)
1. Download the Make PDF From ABC workflow
1. Move `Make PDF From ABC` to `~/Library/Services/`

## Use

1. Right click on any plaintext file containing valid ABC -- multiple tunes is fine
1. You should have a `Make PDF From ABC` contextual menu item (right at the bottom)
1. Click it.
1. Wait a few seconds and you should get a PDF file of the same name as the plaintext file. You might see a `.ps` file pop up for a second -- this is a transitionary file inbetween ABC and PDF.

## How it works

The automator workflow is really just a wrapper for some bash, which just goes through the list of files presented to it by the automator workflow and runs `abcm2ps` and `pd2pdf`. 

The bash is [here](https://github.com/barnabywalters/os-x-abc-to-pdf-service/blob/master/Make%20PDF%20From%20ABC.workflow/Contents/document.wflow#L58) -- it should be really easy to customise/improve, so please do fork if you have other needs! Sorry it's inside a nasty workflow, I shall probably re-write it as an applescript at some point to make customisation easier.
