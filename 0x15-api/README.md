0x15. API
The problem with shell script is that it's so deceptively easy to get started. Once you've started adding each bit of extra complexity seems easier than trashing the whole thing and starting from scratch in a decent language (e.g., Python) with a decent design.

Speaking from personal experience, nearly every time I have used shell script in recent times for something that isn't completely trivial, I have come to regret it. Ugh.

Sometimes you don't have a choice. For example, one time I had to use shell script to create a transparent command line hijacking function for a utility I was working on, and just look at the abomination I am ashamed to have been forced to write:

hijack_command() {
    CALLBACK=$1
    COMMAND=$2
    NEW_COMMAND=$3

    ORIG_COMMAND=$(which $COMMAND 2>/dev/null)

    eval "

        function $COMMAND() {
            args=()
            for arg; do
                args[\${#args[*]}]=\"'\$arg'\"
            done
            if $CALLBACK; then
                eval $NEW_COMMAND \${args[*]}
            else
                if [ \"$ORIG_COMMAND\" ]; then
                    eval $ORIG_COMMAND \${args[*]}
                fi
            fi
        }"
}
When a language forces you to do nested metaprogramming something as trivial as this, run and don't look back!

Have you ever regretted using shell script? Share your thoughts!

Comments
Liraz Siri's picture
Use the best tool for the job
Liraz Siri - Tue, 2010/02/09 - 13:59
My take on this is that a programming language is just a tool. Use the right tool for the job. Depending on what you want to accomplish different languages may be better suited. I use Python for most of my programming these days. It's not a speed demon though there are several very serious efforts to bring it's performance up to par with languages such as Java.
Note that for most applications Python's performance is not an issue at all. In the past when I've needed to squeeze out more performance out of a specific bottleneck in my code I've implemented that part in C and then created bindings to Python.

But heck it's not a religious thing. To this day I still use Perl when I need to write a dirty one-liner.

reply
Jeremy Davis's picture
I was just about to remove your posts...
Jeremy Davis - Thu, 2017/10/19 - 03:25
We're pretty clear on the need for users to not be abusive on our forums, so when I saw this, I was on my way to delete your posts.
But then I realised that you were responding to a spammer (that I had previously missed). TBH, I still think that your language was a little harsh, but I must admit that I sometimes have similar thoughts when spammers waste our time and resources posting their crap!

Have an awesome day! :)
