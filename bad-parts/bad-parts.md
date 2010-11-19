!SLIDE subsection transition=scrollUp

# Bad parts #

!SLIDE bullets incremental transition=scrollUp
# Global variables #

* JavaScript doesn't have a linker
* Uses the global namespace for binding
* As an app grows, bad things happen
* What about mashups?
* Don't pollute the global namespace!
* Like all martial arts requires discipline

!SLIDE bullets incremental transition=scrollUp
# new #

* What happens when you invoke a constructor without new?
* It's a normal function call
* __this__ is bound to the global namespace

!SLIDE execute transition=scrollUp
# != and == #

## Will compare values of different types ##
## ( automatic type coercion ) ##

    @@@ javaScript
    CORE.out( '' == '0' );
    CORE.out( 0 == '' );
    CORE.out( 0 == '0' );
    CORE.out( false == 'false' );
    CORE.out( false == '0' );
    CORE.out( false == undefined );
    CORE.out( false == null );
    CORE.out( null == undefined );
    CORE.out( ' \t\r\n ' == 0 );

## Use __!==__ and __===__ instead ##

!SLIDE bullets incremental transition=scrollUp
# Semicolon insertion #

* Missing semicolons are automatically inserted
* Optional but may cause problems with some minimizers
* It can mask more serious errors
* Don't depend on this

!SLIDE execute transition=scrollUp
# Semicolon insertion #

    @@@ javaScript
    var output = function() {
        return
        {
            status: true
        }
    }();

    CORE.out( output );
    CORE.out( output && output.status );

!SLIDE bullets incremental transition=scrollUp
# eval #

* _eval_ is evil
* Harder to read
* Slower (needs to run the compiler)
* Can compromise security
* Try to avoid it whenever possible

!SLIDE execute transition=scrollUp
# Reserved words #

    @@@ javaScript
    abstract boolean break byte
    case catch char class const continue
    debugger default delete do double
    else enum export extends
    false final finally float for function goto
    if implements import in instanceof int
    interface long native new null
    package private protected public return
    short static super switch synchronized
    this throw throws transient true try typeof
    var volatile void while with

!SLIDE execute transition=scrollUp
# typeof & NaN #

    @@@ javaScript

    CORE.out( typeof null );
    CORE.out( typeof NaN );

    CORE.out( NaN === NaN );
    CORE.out( isNaN(NaN) );

