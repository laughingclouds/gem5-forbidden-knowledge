Every class in this folder describes a component that is used in the [garnet module](https://www.gem5.org/documentation/general_docs/ruby/garnet-2/).
Each class has a `wakeup` function which is called whenever that component is in use.

Use vscode's **outline** for a view of all possible functions and classes declared within a header or source file. You can use this functionality to look for any useful function when attempting tasks.

![[vscode_outline.png]]


> [!quote] [Capabilities of Gem5](https://www.gem5.org/documentation/learning_gem5/introduction/#capabilities-out-of-the-box)
> 
> To get the most out of gem5, you’ll most likely need to add new capabilities specific to your project’s goals. gem5’s modular design should help you make modifications without having to understand every part of the simulator.


A packet usually travels in the following order:

1) PE: Originate from here
2) NetworkInterface: receive packet from PE through NetworkLink
3) Router: source router - receive packet from NI through NetworkLink
4) Router: destination router - receive from NetworkLink
5) NetworkInterface
6) PE: the destination PE

Things may differ depending on what type of packet is being transmitted. But this is the gist of things.

You can refer to this figure to imagine the PE, NI and the Router together

![[pe_ni_router.png]]

But we will need a much more detailed view of these components when diving into the source code. Here it is:
![[pe_ni_router_detailed.png]]


> [!info] About the figure above
> The given figures help in visualising the organisation of the PE, NI, ..., but it's not an exact pictorial representation.
> 
> For example, depending on the type of architecture or maybe even topology used, there might be more than two NI's connected to a single router.
> 
> *You never know* 🤷.

# Processing Element

**There is no processing element**. Or at least, there is no code within the garnet module that represents the processing element.

The garnet module only represents the interconnect after all.

*Well then*, you might ask, *where does the NI receive packets from?*
It's very complicated and the easiest answer is *I don't know*.

What I know however, is that this means the entry point for a packet (at least within garnet) is at the NetworkInterface. The NI has access to a **buffer** that holds the packets to be injected into the network.

What I don't know, is how and where (in the source code) these packets are inserted into the buffer. Packet creation is still a mystery to me (read: I didn't read enough of the source code).