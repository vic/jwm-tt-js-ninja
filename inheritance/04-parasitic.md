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
* Return the new object

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

