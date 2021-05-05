## Monitor index creation

=== "Snippet"

    ```yaml
    db.currentOp(true).inprog.forEach(function(op){ if(op.msg!==undefined) print(op.shard, op.msg) })
    ```

=== "Output"

    ```yaml
    shard0 Index Build Index Build: 90978/1488517 6%
    shard1 Index Build Index Build: 90395/1559205 5%
    shard2 Index Build Index Build: 156994/1467905 10%

    ```
