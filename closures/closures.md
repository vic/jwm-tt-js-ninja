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
    twice(12); // -> 24

!SLIDE bullets transition=scrollUp

# Why do I need them? #

* Real Private access.
* Only expose your API interface.

!SLIDE transition=scrollUp

# Closures Example  #

    @@@ javaScript
    var obtainAPI = function(url) {
        var thisIsPrivate = someOperation(url);
        var doBla = funcion(a, callback) {
            var response = another(thisIsPrivate + a);
            callback(response);
        }
        return {
            exposedMethod: doBlah
        }
    }

    var api = optainAPI("jwmsolutions.com");
    api.exposedMethod("cool", function(resp) {
        console.debug(resp);
    });

