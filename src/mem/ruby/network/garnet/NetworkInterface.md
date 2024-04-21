# Header

[NetworkInterface.hh](https://github.com/gem5/gem5/blob/stable/src/mem/ruby/network/garnet/NetworkInterface.hh) has the class definition for `NetworkInterface`.
Two more classes are defined in `NetworkInterface`:
- `OutputPort`
- `InputPort`

**Analogy:** Imagine an ATM machine. It has a card reader and a cash dispenser. A card is inserted into the card reader and cash is released from the dispenser. Similarly, think of **InputPort** and **OutputPort** as the slots that make it possible.


## Params

GarnetNetworkInterfaceParams is a `SimObject` whose declaration is generated within a header (as `GarnetNetworkInterface.hh`) file when you build the gem5 binary.

Gem5 reads the contents of [`GarnetNetwork.py`](https://github.com/gem5/gem5/blob/115322319c709a6e2a12e8b5c5299aa813d94633/src/mem/ruby/network/garnet/GarnetNetwork.py#L57) to generate this struct.

As its name suggests, it represents all "parameters" the NI may receive when a **NetworkInterface** instance is being initialised.

Gem5 allows a huge number of parameters to be entered through the command line. And this is one of the files to make changes in, if you wish to add custom parameters.