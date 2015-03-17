# PHP-Simple-HTML-DOM-Parser

## Description ##
A simple PHP HTML DOM parser written in PHP5+, supports invalid HTML, and provides a very easy way to handle HTML elements.


http://simplehtmldom.sourceforge.net/manual.htm


## Quick Start ##
###Get HTML elements ###
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

### Modify HTML elements ###
```PHP
// Create DOM from string
$html = str_get_html('<div id="hello">Hello</div><div id="world">World</div>');

$html->find('div', 1)->class = 'bar';

$html->find('div[id=hello]', 0)->innertext = 'foo';

echo $html; // Output: <div id="hello">foo</div><div id="world" class="bar">World</div>
```

### Extract contents from HTML ###
```PHP
// Dump contents (without tags) from HTML
echo file_get_html('http://www.google.com/')->plaintext; 
```

### Scraping Slashdot! ###
```PHP
// Create DOM from URL
$html = file_get_html('http://slashdot.org/');

// Find all article blocks
foreach($html->find('div.article') as $article) {
    $item['title']     = $article->find('div.title', 0)->plaintext;
    $item['intro']    = $article->find('div.intro', 0)->plaintext;
    $item['details'] = $article->find('div.details', 0)->plaintext;
    $articles[] = $item;
}

print_r($articles);
```


## How to create HTML DOM object?##
### Quick way ###
```PHP
// Create a DOM object from a string
$html = str_get_html('<html><body>Hello!</body></html>');

// Create a DOM object from a URL
$html = file_get_html('http://www.google.com/');

// Create a DOM object from a HTML file
$html = file_get_html('test.htm');
```

### Object-oriented way ###
```PHP
// Create a DOM object
$html = new simple_html_dom();

// Load HTML from a string
$html->load('<html><body>Hello!</body></html>');

// Load HTML from a URL 
$html->load_file('http://www.google.com/');

// Load HTML from a HTML file 
$html->load_file('test.htm');
```

### 
