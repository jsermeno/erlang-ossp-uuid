## Erlang OSSP uuid

This is a fork of [erlang-ossp-uuid](https://github.com/yrashk/erlang-ossp-uuid). All credit should be given to this repository. I simply created this repo because I wanted to use this project immediately and felt unsafe without it being tagged with a release.

In your `rebar.config`

    {deps, [
        ...
        {'ossp_uuid', ".*", {
            git, "https://github.com/jsermeno/erlang-ossp-uuid.git", {tag, "0.1.0"}
        }}
    ]}.

Then

    rebar get-deps
    rebar compile

If you want to test real quick you can `cd` into `deps/ossp_uuid/ebin`

    erl
    Eshell V6.0  (abort with ^G)
    1> application:start(ossp_uuid).
    ok
    2> ossp_uuid:make(v4, text).
    <<"2088a6a5-8073-401b-b34b-f7f295eae7ef">>

Version 4 is a uuid that relies on random numbers ([uuid](http://en.wikipedia.org/wiki/Universally_unique_identifier)).
