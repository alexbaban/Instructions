# jQuery Fundamentals

### Include jQuery

``` html
...
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>jQuery Fundamentals</title>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

</head>
<body>
...

```

or if included with Bootstrap

``` html
...
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>jQuery Fundamentals</title>

    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>

</head>
<body>
...

```

## Selectors

### by id, by class name
``` js
$("#some-id").hide();
$(".some-class-name").show();
```

### all span inside all p
``` html
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.  
  <span>Consequuntur, molestias commodi iusto quidem iste eveniet?</span>  
  Distinctio saepe laudantium eaque porro qui eligendi quod provident aspernatur repellat temporibus.</p>

```

``` js
$("p span").css("color", "red");
```

### selector extensions
> jQuery has extended the CSS3 selectors with more selectors. Because these selectors are jQuery extension and not part of the CSS specification, queries using them cannot take advantage of the performance boost provided by the native DOM  querySelectorAll() method. To achieve the best performance when using these selectors, first select some elements using a pure CSS selector, then use .filter().

Link: (https://api.jquery.com/category/selectors/jquery-selector-extensions/)

``` html
<ul id="list">
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>

</ul>
```
**`:first`** *Selects the first matched DOM element.*
``` js
    $('ul#list li:first').css('color', 'red');

```
> Because :first is a jQuery extension and not part of the CSS specification, queries using :first cannot take advantage of the performance boost provided by the native DOM querySelectorAll() method. To achieve the best performance when using :first to select elements, first select the elements using a pure CSS selector, then use .filter(":first").

``` js
    $('ul#list li').filter(':first').css('color', 'red');

```
**more like this**
``` js
    $('ul#list li').filter(':last').css('color', 'green');
    $('ul#list li').filter(':even').css('background-color', 'yellow');
    $('ul#list li').filter(':odd').css('background-color', '#ccc');
    $('ul#list li').filter(':nth-child(3n)').css('list-style', 'none');

```

### selecting `input` by `type`
``` html
    <input type="button" value="Button" />
    <input type="submit" value="Submit" />
    <input type="text" />

```

``` js
    $(':button').hide();
    $(':submit').hide();
    $(':text').hide();

```

### attributes as selectors
``` html
    <a href="http://google.com">Google</a>
    <a href="http://yahoo.com">Yahoo</a>

```

``` js
    $('[href]').css('color', 'red');
    $('a[href="http://yahoo.com"]').css('color', 'green');

```

### select *everything*
``` js
    $('*').hide();

```

## Events


## DOM Manipulation


## Methods


## Effects & Animation


## Ajax
