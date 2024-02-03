Atom.abs illustrate ABS module that keep creating new atoms. To run the simulation:
*  Compile Atom.abs (See [ABS Compiler](https://github.com/abstools/abstools))
*  Edit gen/erl/run -> add `%%! -sname MyNode@MyHost` after line 10 (we will monitor this node using Erlang etop)
*  Create etop script (ex etop.sh) with content: `erl -sname etop -hidden -s etop -node MyNode@MyHost -sort memory` (see [etop guide](https://www.erlang.org/doc/man/etop))
*  Run Atom.abs generated code `gen/erl/run -p 7776` (terminal 1)
*  Run etop script (terminal 2)
*  Send request to `localhost:7776/call/abc/call` (terminal 3)
*  Observe etop terminal (you may need to send 100-1000 requests)
