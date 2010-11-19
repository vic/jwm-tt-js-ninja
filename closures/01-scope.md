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



