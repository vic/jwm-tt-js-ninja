!SLIDE subsection transition=scrollUp

# Modules #

!SLIDE execute transition=scrollUp
# Anonymous functions #

    @@@ javaScript
    my_link.bind('click', function(e) {
        e.preventDefault();
        alert('You cliked the link');
    };

    setTimeout(function() {
        alert('Timeout triggered');
    }, 100);

!SLIDE execute transition=scrollUp
# Scope #

    @@@ javaScript
    (function() {
        var myPrivateProperty = 'hello world';
        CORE.out(myPrivateProperty);
    })();
    CORE.out(typeof myPrivateProperty);

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

