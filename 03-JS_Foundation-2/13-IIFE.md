# IIFE

```js
(function() {
  // local scope
  var a = 'a';
})();

console.log(a); // ReferenceError: a is not defined
```

---

## Immediately Invoked Function Expression

- anonymous()
  - Variable Environment
- Global Execution Context

---

## Version 1

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script>
      var z = 1;
      function a() {
        return 5;
      }
    </script>
    <script>
      var zz = 2;
    </script>
    <script>
      var zzz = 3;
    </script>
    <script>
      var z = 100000;
      function a() {
        return 'hahahaha';
      }
    </script>
  </body>
</html>
```

Console

```js
console.log(a()); // 5

console.log(a()); // hahahaha
```

---

## Version 2

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script>
      var z = 1;
      var script1 = (function() {
        return 5;
      })();
    </script>
    <script>
      var zz = 2;
    </script>
    <script>
      var zzz = 3;
    </script>
    <script>
      var z = 100000;
      function a() {
        return 'hahahaha';
      }
    </script>
  </body>
</html>
```

Console

```js
console.log(a()); // hahahaha
```

---

## Version 3

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script>
      var z = 1;
      var script1 = (function() {
        function a() {
          return 5;
        }
        return {
          a: a
        };
      })();
    </script>
    <script>
      var zz = 2;
    </script>
    <script>
      var zzz = 3;
    </script>
    <script>
      var z = 100000;
      function a() {
        return 'hahahaha';
      }
    </script>
  </body>
</html>
```

Console

```js
console.log(a()); // hahahaha

console.log(script1.a()); // 5
```

---

## Version 4 jQuery

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
      var z = 1;
      var script1 = (function() {
        $('h1').click(function() {
          $('h1').hide();
        });
        return {};
      })();
    </script>
  </body>
</html>
```

Console

```js
window.$;

window.jQuery;
```

---

## Version 5 jQuery + parameter

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
      var z = 1;
      var script1 = (function(OMG) {
        OMG('h1').click(function() {
          OMG('h1').hide();
        });
        return {};
      })(jQuery);
    </script>
  </body>
</html>
```

---

## Version 6 jQuery + parameter

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <h1>Hellooooo</h1>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
      var z = 1;
      var script1 = (function($) {
        $('h1').click(function() {
          $('h1').hide();
        });
        return {
            $: 'hi';
        };
      })(jQuery);
    </script>
  </body>
</html>
```

Console

```js
script.$; // hi
```
