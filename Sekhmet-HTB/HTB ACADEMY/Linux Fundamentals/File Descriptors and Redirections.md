1. Data Stream for Input
    - `STDIN – 0`
2. Data Stream for Output
    - `STDOUT – 1`
3. Data Stream for Output that relates to an error occurring.
    - `STDERR – 2`


| Commands        | Description                                   |
| --------------- | --------------------------------------------- |
| `2 > flop.txt`  | Over write the non-valid stuff in flop.txt    |
| `2 > /dev/null` | Over write the non-valid stuff in `/dev/null` |
| `1 > good.txt`  | Over wrte the valid stuff in good.txt         |
| `1 >> good.txt` | Write (add only) the valid stuff in good.txt  |

`/dev/null` = Directory to discard stuff, all the data that goes here is gonna be delete
`> or <` = Redirect/ Over write and output to a specific file (if not existing : create new one)
`>> or <<` = Same as `> or <`  but just writing the output not over
`|` = Use the `STDOUT` from one program to be processed by another generally using grep



