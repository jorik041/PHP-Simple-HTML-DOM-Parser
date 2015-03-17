# PHP-Simple-HTML-DOM-Parser

## Description ##
A simple PHP HTML DOM parser written in PHP5+, supports invalid HTML, and provides a very easy way to handle HTML elements.


http://simplehtmldom.sourceforge.net/manual.htm


## Quick Start ##
```PHP
// Create DOM from URL or file
$html = file_get_html('http://www.google.com/');

// Find all images 
foreach($html->find('img') as $element) 
       echo $element->src . '<br>';

// Find all links 
foreach($html->find('a') as $element) 
       echo $element->href . '<br>';
```
