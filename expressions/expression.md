!SLIDE subsection transition=scrollUp

# Statements / Expressions #

!SLIDE bullets transition=scrollUp
# Expression #
## always yields a value ##

    @@@ javaScript
    "Hello World"
    foo = 3.1459 * 2
    mux = foo == bar ? baz : qux

!SLIDE bullets transition=scrollUp
# Statement #
## just _do_ something ##

    @@@ javaScript
    if(cond) { expr } else { expr2 }
    while(cond) { expr }
    for(init; cond; incr) { expr }
    for(var idx in object) { expr }

!SLIDE execute transition=scrollUp
# Statement vs Expression #
## Statement dont yield value ##

    @@@ javaScript
    // Syntax error !
    // Tried to use statement as expression.
    result = if(1 > 2) { "hm" } else { "uh?" }



