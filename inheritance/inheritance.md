!SLIDE subsection

# Inheritance #

!SLIDE bullets incremental
# Prototypal inheritance #

* No classes in JavaScript, only objects
* Objects inherit directly from other objects
* What matters is what an object can do, not the lineage
* JavaScript supports many code reuse patterns

!SLIDE execute
# Constructors #

    @@@ javaScript
    var Cat = function(name) {
        this.name = name;
    };

    var myCat = new Cat("micha");
    CORE.out( myCat.name );

!SLIDE execute
# Constructor prototype #

    @@@ javaScript
    var Cat = function(name) {
        this.name = name;
    };
    Cat.prototype.get_name = function() {
        CORE.out( this.name );
    };
    Cat.prototype.say_meow = function() {
        CORE.out( 'meow' );
    };

    var myCat = new Cat("micha");
    myCat.get_name();
    myCat.say_meow();

!SLIDE execute
# Pseudoclassical inheritance #

    @@@ javaScript
    var Cat = function(name) { this.name = name; };
    Cat.prototype.say_meow = function() {
        CORE.out('meow');
    };

    var Kitten = function(name) {
        this.name = name;
    };
    Kitten.prototype = new Cat();
    Kitten.prototype.purr = function() {
        CORE.out('r-r-r-r-r');
    };
    var myKitten = new Kitten("catrin");
    CORE.out(myKitten.name);
    myKitten.say_meow();
    myKitten.purr();

!SLIDE bullets incremental
# Problems #

* No encapsulation
* Weird sintax
* Duplication of code (constructors)

!SLIDE execute
# Pure prototypal inheritance #

    @@@ javaScript
    Object.create = function(o) {
        var F = function() {};
        F.prototype = o;
        return new F();
    };

!SLIDE execute
# Pure prototypal inheritance #

    @@@ javaScript
    var cat = {
        name: "",
        get_name: function() {
            CORE.out(this.name);
        },
        say_meow: function() {
            CORE.out('meow');
        }
    };

    var myCat = Object.create(cat);
    myCat.name = "micha";
    myCat.get_name();
    myCat.say_meow();

!SLIDE execute

    @@@ javaScript
    var cat = {
        name: "",
        get_name: function() {
            CORE.out(this.name);
        }
    };
    var kitten = Object.create(cat);
    kitten.name = "catrin";
    kitten.say_meow = function() {
        CORE.out('meow');
    };

    kitten.get_name();
    kitten.say_meow();

!SLIDE bullets incremental
# Pure prototypal inheritance #

* Very simple
* No longer need to use __new__
* Don't have to worry about __prototype__
* Still no encapsulation

!SLIDE bullets incremental
# Power constructors #

* Object factories
* Use functions to have scope
* Very similar to singleton pattern

!SLIDE execute

    @@@ javaScript
    var cat = function(name) {
        var meow = 'meow';
        var do_meow = function() {
            CORE.out(meow);
        };
        return {
            get_name: function() {
                CORE.out(name);
            },
            say_meow: function() {
                do_meow();
            }
        };
    };
    var myCat = cat("micha");
    CORE.out(typeof myCat.name);
    myCat.get_name();
    myCat.say_meow();
    CORE.out(typeof myCat.do_meow);

!SLIDE bullets incremental
# "Parasitic" inheritance #

* Create a new object
* Add private variables and methods
* Augment the new object with methods
* Return the new method

!SLIDE execute

    @@@ javaScript
    var cat = function(spec) {
        var that = {};
        var do_meow = function() {
            CORE.out('meow');
        };

        that.get_name = function() {
            CORE.out(spec.name);
        };
        that.say_meow = function() {
            do_meow();
        };
        return that;
    };

    var myCat = cat({name: 'micha'});
    CORE.out(typeof myCat.name);
    myCat.get_name();
    myCat.say_meow();
    CORE.out(typeof myCat.do_meow);

!SLIDE execute

    @@@ javaScript
    var cat = function(spec) {
        return {
            get_name: function() {
                CORE.out(spec.name);
            }
        };
    };
    var kitten = function(spec) {
        var that = cat(spec);
        var do_purr = function() {
            CORE.out('r-r-r-r-r');
        };
        that.purr = function() {
            do_purr();
        };
        return that;
    };
    var myKitten = kitten({name: 'catrin'});
    myKitten.get_name();
    myKitten.purr();

