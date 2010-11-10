!SLIDE subsection

# Objects #

!SLIDE

# Think of them as light hashmaps. #

    @@@ javaScript
    var person = { name: "Joe" age: 28 };

!SLIDE

# Everything is accessible. #

    @@@ javaScript
    person.name = "Bad"
    person["name"] = "Ugly"


!SLIDE subsection

# Arrays #

!SLIDE
# Untyped collections #

     @@@ javaScript
     var clients = [ posadas, telcel, palacio ]
     clients.length // -> 3

!SLIDE
# Undefined values #
## pretty much everything not available in scope ##

      @@@ javaScript
      typeof(something) == "undefined"

