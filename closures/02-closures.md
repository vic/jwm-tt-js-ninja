!SLIDE subsection transition=scrollUp

# Closures #

!SLIDE transition=scrollUp

# Closures ? #

# Capturing the lexical scope #
## Yes, pretty simple concept ##

    @@@ javaScript
    var mult = function(a) {
        return function(b) {
            return a * b;
        }
    }
    var twice = mult(2);
    CORE.out( twice(12) );
    CORE.out( mult(12)(12) );

!SLIDE bullets transition=scrollUp

# Why do I need them? #

* Real Private access.
* Only expose your API interface.

!SLIDE transition=scrollUp

# Closures Example  #

    @@@ javaScript
    var obtainAPI = function(url) {
        var thisIsPrivate = someOperation(url);
        var foo = funcion(a, callback) {
            var res = foo(thisIsPrivate + a);
            callback(res);
        }
        return {
            exposedMethod: doBlah
        }
    }

    var api = optainAPI("jwmsolutions.com");
    api.exposedMethod("cool", function(resp) {
        console.debug(resp);
    });

