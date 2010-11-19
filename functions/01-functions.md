!SLIDE subsection transition=scrollUp

# Functions #

!SLIDE bullets incremental transition=scrollUp
# Functional language #

* Functions are first class citizens
* Functions are objects
* Only way to have scope

!SLIDE execute transition=scrollUp
# Function definition statement #
## imperative style ##

    @@@ javaScript
    // statement
    function foo() {}

    CORE.out( typeof foo );

!SLIDE execute transition=scrollUp
# Function definition expression #
## functional style ##

    @@@ javaScript
    // expression
    var foo = function() {}

    CORE.out( typeof foo );


!SLIDE execute transition=scrollUp
# But wait .. what if I try to combine them #

    @@@ javaScript
    var foo = function bar() {}

    CORE.out( typeof foo ); // function
    CORE.out( typeof bar ); // undefined

!SLIDE execute transition=scrollUp
## Always use try to use expressions ###

    @@@ javaScript
    // Assign anonymous functions to
    // scoped variables.
    var foo = function() {  }


!SLIDE bullets incremental transition=scrollUp
# Function #

* Functions blocks of code (create an scope) that can be activated.
* They dont even need a name
* They dont need a fixed set of parameters

!SLIDE execute transition=scrollUp
# Anonymous funtions #
## dont need to be named ##

    @@@ javaScript
    (function(msg){
      alert("hello "+msg);
     })("world");

!SLIDE execute transition=scrollUp
# Anonymous funtions #
## weak typed / unchecked arity ##

    @@@ javaScript
    var fun = function(a, b) {
      CORE.out( a + b );
    }
    fun();
    fun("hey");
    fun("whats", "up");
    fun(14, 10);
    fun("weak", 10);

!SLIDE transition=scrollUp
# dynamic function arguments #
## you can use the special __arguments__ object ##

    @@@ javaScript
    var fun = function() { // no parameter names
       CORE.out(arguments.length);
       var name = arguments[0];
       if("function" === typeof(arguments[1])) {
         CORE.out("second argument is a function");
       }
    }
    fun();
    fun("hey", function() { foo }, "this");

!SLIDE execute transition=scrollUp
# Self referencing functions #
## __arguments.callee__ holds a reference to itself ##

    @@@ javaScript
    var fun = function() {
       CORE.out( arguments.callee.toString() );
    }
    fun();

!SLIDE transition=scrollUp
# Self referencing functions #
## __arguments.callee__ holds a reference to itself ##

    @@@ javaScript
    var fun = function(arg) {
       // the function being executed
       var self = arguments.callee;

       // this can be useful for memoizing data
       var cache = self.cache || {}
         , value = self.cache[arg] || exp(arg);
       self.cache[arg] = value;

       return cached;
    }
    fun("something");

