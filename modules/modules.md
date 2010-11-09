!SLIDE subsection

# Modules #

!SLIDE execute
# Anonymous functions #

    @@@ javaScript
    my_link.bind('click', function(e) {
        e.preventDefault();
        alert('You cliked the link');
    }

    setTimeout(function() {
        alert('Timeout triggered');
    }, 100);

!SLIDE execute
# Scope #

    @@@ javaScript
    (function() {
        var myPrivateProperty = 'hello world';
        CORE.out(myPrivateProperty);
    })();
    CORE.out(typeof myPrivateProperty);

!SLIDE execute
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
                return myPrivateMethod();
            }
        }
    })();
    CORE.out(mySingleton.doSomething());
    CORE.out(mySingleton.myPrivateVar);

