<!-- note marker start -->
NOTE: This repo contains only the documentation for the private BoltsOps repo code.
Original file: https://github.com/boltops-pro/upcheck/blob/master/app/files/lambda-function/vendor/up/lib/up/help/completion.md
The docs are publish so they are available for interested subscribers.
For access to the source code, you can become a BoltOps subscriber.
See: https://learn.boltops.com

<!-- note marker end -->

## Examples

    up completion

Prints words for TAB auto-completion.

    up completion
    up completion hello
    up completion hello name

To enable, TAB auto-completion add the following to your profile:

    eval $(up completion_script)

Auto-completion example usage:

    up [TAB]
    up hello [TAB]
    up hello name [TAB]
    up hello name --[TAB]
