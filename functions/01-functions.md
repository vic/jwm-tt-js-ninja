!SLIDE subsection

# Functions #

!SLIDE bullets incremental
# Functional language #

* Functions are first class citizens
* Functions are objects
* Function statement vs function expression
* Only way to have scope

!SLIDE bullets incremental
# Function #

* Functions blocks of code (create an scope) that can be activated.
* They dont care about having a name
* They dont care about defining arguments

!SLIDE
# Anonymous funtions #
# They dont care about having a name #

    @@@ javaScript
    (function(msg){ alert("hello "+msg); })("world");

!SLIDE
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

!SLIDE
# Anonymous funtions #
# They dont care about defining arguments #

    @@@ javaScript
    var fun = function() { // no argument list .. but
       alert(arguments.length); // not a real array though
    }
    fun();
    fun("hey", "thats" "cool");

!SLIDE
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

