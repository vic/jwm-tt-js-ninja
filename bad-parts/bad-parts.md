!SLIDE subsection

# Bad parts #

!SLIDE bullets incremental
# Global variables #

* JavaScript doesn't have a linker
* Uses the global namespace for binding
* As an app grows, bad things happen
* What about mashups?
* Don't pollute the global namespace!

!SLIDE bullets incremental
# new #

* What happens when you invoke a constructor without new?
* It's a normal function call
* __this__ is bound to the global namespace

!SLIDE execute
# Scope #

## No block scope in JavaScript ##

    @@@ javaScript
    var foo = function() {
        var a = 'test';
        if ( a === 'test' ) {
            var b = true;
        }
        CORE.out(b);
    }();
    CORE.out(foo);
## Declare variables at the start of functions ##

!SLIDE execute
# != and == #

## Will compare values of different types ##

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

!SLIDE
# Semicolon insertion #

!SLIDE
# eval #

