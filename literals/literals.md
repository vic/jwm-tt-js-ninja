!SLIDE subsection transition=scrollUp

# Objects #

!SLIDE transition=scrollUp

# Think of them as light hashmaps. #

    @@@ javaScript
    var person = { name: "Joe", age: 28 };

!SLIDE transition=scrollUp

# Everything is accessible. #

    @@@ javaScript
    person.name = "Bad";
    person["name"] = "Ugly";


!SLIDE subsection transition=scrollUp

# Arrays #

!SLIDE execute transition=scrollUp
# Untyped collections #

    @@@ javaScript
    var clients = [
        'posadas', 'telcel', 'palacio'
    ];
    result = clients.length; // -> 3

!SLIDE execute transition=scrollUp
# Undefined values #
## pretty much everything not available in scope ##

    @@@ javaScript
    result = typeof(something) === "undefined";

