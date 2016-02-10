# YouTube HTML parser:<br>to output a list of simple URIs and titles

Syntax:

    cat example.html | youtube-html-parser-to-simple-uri-and-title

## Example

Example input such as a typical YouTube list of related videos:

    <a href="/watch?v=100" ... title="Lorem ipsum" ... >
    <a href="/watch?v=200" ... title="Dolor sit amet" ... >
    <a href="/watch?v=300" ... title="Consectetur adipiscing" ... >

Example output:

    https://www.youtube.com/watch?v=100 Lorem ipsum
    https://www.youtube.com/watch?v=200 Dolor sit amet
    https://www.youtube.com/watch?v=300 Consectetur adipiscing

Example that selects matching title text, then sorts by the title field:

    cat example.html |
    youtube-html-parser-to-simple-uri-and-title |
    grep -i 'best of' |
    sort -k2

## Implementation

This implementation does quick-and-dirty parsing of real world HTML.

TODO: upgrade from simple grep to real HTML parsing.
