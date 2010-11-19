!SLIDE subsection transition=scrollUp
# Underscore.js #

!SLIDE bullets incremental transition=scrollUp
# Functional Programming #

* Collection of useful functions
* Everything under the _ namespace.
* Functional style programming.

!SLIDE bullets incremental transition=scrollUp
# Underscore / Objects #
* keys/values
* extend
* clone
* tap
* mixin to add your functions (don't augment the basic types)


!SLIDE bullets incremental transition=scrollUp
# Underscore / Collections #

* each
* map/reduce
* sortBy
* select/reject/include/all

!SLIDE execute transition=scrollUp
# Underscore Collections Example #

    @@@ javaScript
    // object-oriented way
    _(['John', 'Paul', 'George', 'Ringo']).each(function(beatle) {
        console.log(beatle);
    });

    // functional way
    _.each(['John', 'Paul', 'George', 'Ringo'], function(beatle) {
       console.log(beatle);
    });

    _.reduce([1.5,2,3.7], 0, function(memo, num) { return memo + Math.floor(num) });
    // => 6

    var beatles = [
     {name: 'John', dead: true},
     {name: 'Paul', dead: false},
     {name: 'Ringo', dead: false},
     {name: 'George', dead: true}
    ]

    _.pluck(beatles, 'name');

!SLIDE bullets incremental transition=scrollUp
# Underscore / Functions #
* defer
* bind
* compose
* memoize

