!SLIDE subsection transition=scrollUp

# Basic types #

!SLIDE bullets incremental transition=scrollUp
# Augmenting the basic types #

* Function.prototype
* Object.prototype
* String.prototype
* Array.prototype
* Number.prototype

!SLIDE execute transition=scrollUp
# Integer part of a number #

    @@@ javaScript
    Number.prototype.integer = function() {
        return Math[this < 0 ? 'ceil' : 'floor'](this);
    };

    var a = 10, b = 10.21, c = -12.84;

    CORE.out(a.integer());
    CORE.out(b.integer());
    CORE.out(c.integer());

!SLIDE execute transition=scrollUp
# Function chaining #

    @@@ javaScript
    Function.prototype.andThen = function(g) {
        var f = this;
        return function() {
            f();
            g();
        };
    };

    var sayHi = function() { 
        CORE.out('Hello, world!');
    };
    var sayBye = function() {
        CORE.out('Goodbye!');
    };

    sayHi.andThen(sayBye)();

!SLIDE execute small transition=scrollUp
# Callback manager #

    @@@ javaScript
    Function.prototype.andThen = function(g) {
        var f = this; return function() { f(); g(); };
    };
    var Manager = function() {
        this.callback = function() {};
        this.registerCallback = function(f) {
            this.callback = (this.callback).andThen(f);
        };
    };
    var sayHi = function() { CORE.out('Hello, world!'); };
    var sayBye = function() { CORE.out('Goodbye!'); };

    var manager = new Manager();
    manager.registerCallback(sayHi);
    manager.registerCallback(sayBye);
    manager.registerCallback(sayHi);
    
    manager.callback();
