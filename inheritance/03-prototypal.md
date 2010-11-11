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
* "Differential" inheritance
* No longer need to use __new__
* Don't have to worry about __prototype__
* Still no encapsulation

