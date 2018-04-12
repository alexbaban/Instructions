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

## Events


## DOM Manipulation


## Methods


## Effects & Animation


## Ajax
