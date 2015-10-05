PHP class for creating and displaying PNG userpics based on users' input data, such as email or any other personalized information.

Class generates images like Gravatar service does.

Not compatible with PHP version < 5

Uses GD and **PHP >= 5.3.0**

If you want to make it work on PHP less than 5.3.0, find string

```
array_walk($shape, function(&$coord, $index, $mult) { $coord *= $mult; }, self::SPRITE_SIZE);
```

and rewrite it using _create\_function()_ instead of lambda-function:

```
array_walk($shape, create_function('&$coord, $index, $mult', '$coord *= $mult;'), self::SPRITE_SIZE);
```

**Usage:**

```
$av = new Avatarco;
$av->init('email or other data', 100);
$savedImage = $av->SavePicture('./'); //to save image on disk and return its path
```
or
```
$av->ShowPicture(); // to display image
```

Working demo can be found at http://uf8.ru/avatarco.php (reload for random image)