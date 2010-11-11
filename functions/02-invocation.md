!SLIDE bullets incremental transition=scrollUp
# Function invocation patterns #

* Function invocation pattern
* Method invocation pattern
* Constructor invocation pattern
* Apply / Call invocation pattern

!SLIDE execute transition=scrollUp
# Function #

## Function is __not__ a property of an object ##
## __this__ is bound to the global object ##

    @@@ javaScript

    window.name = 'John';
    var get_name = function() {
        return this.name;
    };
    result = get_name();

!SLIDE execute transition=scrollUp
# Method #

## Function __is__ a property of an object ##
## __this__ is bound to that object ##

    @@@ javaScript

    var person = {
        name: 'John Lennon',
        get_name: function() {
            return this.name;
        }
    };
    result = person.get_name();

!SLIDE execute transition=scrollUp
# Constructor #

## Function is invoked with __new__ prefix ##
## __this__ is bound to a new object ##
## The object will have a hidden link to the function's prototype ##

    @@@ javaScript

    var Person = function() {
        this.name = 'John';
    };
    var someone = new Person();
    var someone_else = new Person();
    CORE.out(someone === someone_else);
    CORE.out(someone.name === someone_else.name);

!SLIDE execute transition=scrollUp
# Apply / Call #

## Functions can have methods ##
## _apply_ and _call_ are methods of _Function_ ##
## We can choose the value of __this__ ##

    @@@ javaScript
    var person = {
        greet: function() {
            return 'Hello ' + (this.name || '');
        }
    };
    CORE.out( person.greet() );
    CORE.out( person.greet.apply({name: 'John'}) );

!SLIDE execute transition=scrollUp
# Apply / Call #

    @@@ javaScript
    var add = function() {
        var i, sum = this.memory || 0;
        for (i = 0; i < arguments.length; i++) {
            sum += arguments[i];
        }
        return (this.memory = sum);
    };
    CORE.out( add(1, 2, 3) );
    CORE.out( add.apply({memory: 10}, [1, 2, 3]) );

    CORE.out( add.call({memory: 21}, 1, 2, 3, 4) );
