Some interesting questions about the router object before I forget.

Where does the router get its id from?

`m_id` is a `unit32_t` belonging to `gem5::ruby::BasicRouter`. It is ID relative to other routers in the system.

It seems like the ID is part of the parameters passed into the router when it is initialised. So is the value for `m_id` coming from **outside**?

1) Routers are initialised within `GarnetNetwork`
2) `GarnetNetwork` takes a `gem5::GarnetNetworkParams` struct object. This is a generated struct (see `GarnetNetwork.py`).
3) `GarnetNetworkParams` inherits from `gem5::RubyNetworkParams`.
4) `RubyNetworkParams` is another generated struct and contains `routers` parameter (see `/src/mem/ruby/network/Network.py`).


> [!todo] look into
> `gem5:GarnetRouterParams`
> Don't forget, `GarnetRouterParams` is a struct generated using the python class `GarnetRouter`. It will be interesting to see how this is achieved.
