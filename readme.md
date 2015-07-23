# VerneMQ Demo Plugin

This plugin demonstrates how you can develop an Authentication/Authorization plugin for VerneMQ. The important files are:

- src/vernemq_demo_plugin.erl 
- src/vernemq_demo_plugin.app.src

The rest is the Erlang OTP application boilerplate.


You must have a recent version of Erlang installed (it's recommended to use the same one VerneMQ is compiled for, typically > 17)

    ./rebar get-deps
    ./rebar compile

Then enable the plugin

    vmq-admin plugin enable --name vernemq_demo_plugin --path <PathToYourPlugin>/vernemq_demo_plugin

Depending on how VerneMQ is started you might need ``sudo`` rights to access ``vmq-admin``.
Moreover the ``<PathToYourPlugin>`` should be accessible by VerneMQ (file permissions).

Since this demo plugin implements hooks which are already covered by ``vmq_passwd`` and ``vmq_acl`` you might want to disable these in order to see the effect of this plugin.

    vmq-admin plugin disable --name vmq_passwd
    vmq-admin disable plugin --name vmq_acl

That's it!
