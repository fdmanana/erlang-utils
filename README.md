# erl_dial.erl

Add the following line to the file ~/.erlang:

<pre>	code:add_patha("/my/path/erlang-utils").</pre>

Some examples follow.

List all couch_file gen_servers:
<pre>
7> erl_diag:print( [ {filter_by, {initial_call, {couch_file, init, 1}}} ] ).

Process <0.107.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 6032
        reductions                              : 924

Process <0.111.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 6744
        reductions                              : 1782

Process <0.119.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 4880
        reductions                              : 924
ok
</pre>

Top 3 couch_file gen_servers using most memory:

<pre>
8> erl_diag:print( [ {filter_by, {initial_call, {couch_file, init, 1}}}, {limit, 3}, {sort_by, total_heap_size}, desc] ).

Process <0.241.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 15792
        reductions                              : 1831

Process <0.172.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 14640
        reductions                              : 4768

Process <0.185.0>

        initial_call                            : {couch_file,init,1}
        status                                  : waiting
        message_queue_len                       : 0
        total_heap_size                         : 14640
        reductions                              : 8985
ok
</pre>
