TIP #1

When testing a URL validation function remember to play with encoding schemes, sometimes double encoding is enough, also remember that an URL has a syntax that can be pretty useful for testing.

URI = scheme:[//authority]path[?query][#fragment]

authority = [userinfo@]host[:port]

Cookies cannot be shared cross domain, so when dealing with authentication tokens cross domain they must be send using other ways, some bugs were found using the above trick.

https://en.wikipedia.org/wiki/List_of_URI_schemes

================================================================================================================================================================================================

TIP #2

Whenever testing parameters taken from a URL to do some task, like this example here:

https://www.digits.com/login?consumer_key=9I4iINIyd0R01qEPEwT9IC6RE&host=https://www.periscope.tv

Here the <host> parameters is where the auth data is sent to, do not forget HTTP Parameter Poluttion attacks (HPP). For sure the https://www.periscope.tv is gonna be well validated, but what happens if try something like this:

https://www.digits.com/login?consumer_key=9I4iINIyd0R01qEPEwT9IC6RE&host=https://www.periscope.tv&host=https://attacker.com


TIP #3

When testing for CSRF there are some things to always do:

*Most of the time state changing ops are done via POST, try changing the request method to GET.

*Try to understand how the token is used, and if is reusable try to get a way to get users tokens, this might be not explotaible but in the past some bugs were exploited because tokens were only tied to username/email and not to username/password.

http://yasserali.com/hacking-paypal-accounts-with-one-click/

TIP #4


TIP #5

TIP #6

TIP #7

TIP #8

TIP #9

TIP #10

TIP #11

TIP #12

TIP #13

TIP #14

TIP #15

TIP #16
