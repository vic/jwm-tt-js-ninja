!SLIDE subsection transition=scrollUp

# Functions #

!SLIDE bullets incremental transition=scrollUp
# Functional language #

* Functions are first class citizens
* Functions are objects
* Only way to have scope

!SLIDE execute transition=scrollUp
# Statement vs Expression #

    @@@ javaScript
    // statement
    function foo() {}

    // expressions
    var foo = function foo() {};
    var foo = function() {};

    var fibonacci = function fib(n) {
        return n < 2 ? n : fib(n-1) + fib(n-2);
    };

    CORE.out( typeof fib );
    CORE.out( fibonacci(10) );

!SLIDE bullets incremental transition=scrollUp
# Function #

* Functions blocks of code (create an scope) that can be activated.
* They dont care about having a name
* They dont care about defining arguments

!SLIDE transition=scrollUp
# Anonymous funtions #
# They dont care about having a name #

    @@@ javaScript
    (function(msg){ alert("hello "+msg); })("world");

!SLIDE transition=scrollUp
# dynamic function arguments #
# They dont care about defining arguments #

    @@@ javaScript
    var fun = function() { // no argument list .. but
       alert(arguments.length); // not a real array though
       // bad thing is you have to manually obtain and
       // determine earch argument meaning.
       var name = arguments[0];
       if(! arguments[1]) {
         // no second argument provided.
       }
    }
    fun();
    fun("hey", "thats" "cool");

!SLIDE transition=scrollUp
# Anonymous funtions #
# They dont care about defining arguments #

    @@@ javaScript
    var fun = function() { // no argument list .. but
       alert(arguments.length); // not a real array though
    }
    fun();
    fun("hey", "thats" "cool");

!SLIDE transition=scrollUp
# Self referencing funtions #
# Functions are just values #

    @@@ javaScript
    var fun = function(arg) { // no argument list .. but
       var self = arguments.callee ; // the function being executed

       // this can be useful for memoizing data
       self.cache = self.cache || {}
       var cached = self.cache[arg] || expensiveOperation(arg);
       return cached;
    }
    fun("something");

