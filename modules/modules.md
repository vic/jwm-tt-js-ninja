!SLIDE subsection transition=scrollUp

# Encapsulation #

!SLIDE bullets transition=scrollUp

# Plain javascript objects #

## having values/functions as properties ##

!SLIDE execute transition=scrollUp
# Singleton with encapsulation #

    @@@ javaScript
    var mySingleton = (function() {
        var myPrivateVar = 'hello world';
        // more private vars
        var myPrivateMethod = function() {};
        // more private methods
        return {
            doSomething: function() {
                return myPrivateVar.toUpperCase();
            },
            doSomethingElse: function() {
                myPrivateMethod();
            }
        };
    })();
    CORE.out(mySingleton.doSomething());
    CORE.out(mySingleton.myPrivateVar);

