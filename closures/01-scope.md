!SLIDE subsection transition=scrollUp

# Scope #

!SLIDE execute transition=scrollUp

# Local Variables #

    @@@ javaScript
    var fun = function() {
      var baz = "Hello World";
      CORE.out(baz);
    }
    fun();
    CORE.out( typeof baz );

!SLIDE execute transition=scrollUp

# Free Variables #

    @@@ javaScript
    var baz = "Hello World";
    var fun = function() { CORE.out(baz); }
    fun();
    baz = "Goodbye World";
    fun();


!SLIDE execute transition=scrollUp
# Scope #

## No block scope in JavaScript ##

    @@@ javaScript
    var foo = function() {
        var a = 'test';
        if ( a === 'test' ) {
            var b = true;
        }
        CORE.out(b);
    }();
    CORE.out(foo);
## Declare variables at the start of functions ##

