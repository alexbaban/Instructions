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

## Document Ready

``` js
$(document).ready(function() {
  // run code after document is loaded

});

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
> jQuery has extended the CSS3 selectors with more selectors. 

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

Link: (https://api.jquery.com/category/selectors/jquery-selector-extensions/)

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

## Mouse Events

### mouse click on a button with an id of 'btn-one'
``` js
$('#btn-one').click(function(evt) {
    alert("button one clicked");
    console.log(evt);
});

// or

$('#btn-one').on('click', function() {
    alert("button one clicked");
});

// or

$('#btn-one').on('click', function() {
    $('#list').toggle();
});

```

### mouse hover, mouseenter, mouseleave
``` js
$('#btn-one').hover(function() {
    $('#list').toggle();
});

// equivalent with

$('#btn-one').on('mouseenter', function() {
    $('#list').toggle();
});

// together with

$('#btn-one').on('mouseleave', function() {
    $('#list').toggle();
});

```

## Form Events

``` html
<form>
    <label>Name</label><br />
    <input type="text" id="name" />
    <br />
    <label>Email</label><br />
    <input type="email" id="email" />
    <br />
    <label>Gender</label><br />
    <select id="gender">
        <option value="male">Male</option>
        <option value="female">Female</option>
    </select>
    <br />
    <input type="submit" value="Submit" />
        

</form> 

```

### focus
``` js
$('input').focus(function(evt) {
    $(this).css('background', 'lightblue');
});

$('input').blur(function(evt) {
    $('input').css('background', 'white');
});

```

### keyup, keydown
``` js
$('input').keyup(function(evt) {
    console.log(evt.target.value);
});

```

### change
``` js
$('select#gender').change(function(evt) {
    console.log(evt.target.value);
});

```

### submit
``` js
$('form').submit(function(evt) {
    evt.preventDefault();
    console.log(evt);
});

```

## DOM Manipulation

``` css
.my-class {
    color: whitesmoke;
    background: chocolate;
}

```

``` html
<button id="btn1">Button</button>
<p id="para1">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Tempora mollitia ut quos dolores?</p>
<p id="para2" class="my-class">Lorem ipsum dolor sit amet consectetur adipisicing.</p>

<div id="my-div"></div>

<a href="//google.com">Google</a>

```

### add, remove, toggle class
``` js
$('#para1').addClass('my-class');
$('#para2').removeClass('my-class');

$('#btn1').click(function() {
    $('#para1').toggleClass('my-class');
});

```

### set, get content
``` js
$('#my-div').text('Hello!');
$('#my-div').html('<h2>Hello World</h2>');

var myText = $('#my-div').text();
console.log(myText);

```

### wrap
``` js
$('p').wrap('<h3>');
$('p').wrapAll('<h3>');
```

### more
``` js
.append();
.prepend();
.appendTo();
.prependTo();
.before();
.after();
.empty();
.detach();

```

### attributes
``` js
$('a').attr('target', '_blank');
console.log( $('a').attr('href') );
$('a').removeAttr('target', '_blank');

```

### append from input
``` html
<input id="new-text" type="text" />
<ul id="my-list">
    <li>item one</li>
    <li>item two</li>
    <li>item three</li>
</ul>

```

``` js
// enter key code is 13
$('#new-text').keyup(function(e) {
    if (e.which === 13) {
        e.preventDefault();
        $('#my-list').append('<li>'+ e.target.value +'</li>');
        $('#new-text').val('');
    }
});

```

### arrays
``` js
var myArr = ['Alpha', 'Bravo', 'Charlie', 'Delta', 'Echo'];

// append
$.each(myArr, function(i, val) {
    $('#my-list').append('<li>'+ val +'</li>');
});

// get
var newArr = $('#my-list li').toArray();
console.log(newArr);

$.each(newArr, function(i, val) {
    console.log(val.innerHTML);
});

```

## Methods


## Effects & Animation


## Ajax
