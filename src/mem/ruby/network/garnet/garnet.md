Every class in this folder describes a component that is used in the [garnet module](https://www.gem5.org/documentation/general_docs/ruby/garnet-2/).
Each class has a `wakeup` function which is called whenever that component is in use.

Use vscode's **outline** for a view of all possible functions and classes declared within a header or source file. You can this functionality to look for any useful function when attempting tasks.

![[vscode_outline.png]]


> [!quote] [Capabilities of Gem5](https://www.gem5.org/documentation/learning_gem5/introduction/#capabilities-out-of-the-box)
> 
> To get the most out of gem5, you’ll most likely need to add new capabilities specific to your project’s goals. gem5’s modular design should help you make modifications without having to understand every part of the simulator.


A packet may travel in the following order:

1) PE: Originate from here
2) NetworkInterface: receive packet from PE through NetworkLink
3) Router: source router - receive packet from NI through NetworkLink
4) Router: destination router - receive from NetworkLink
5) NetworkInterface
6) PE: the destination PE

Things may differ depending on what type of packet is being transmitted. But this is the gist of things.

You can refer to this figure to imagine the PE, NI and the Router together:
![[pe_ni_router.png]]

But we will need a much more detailed view of these components when diving into the source code. Here it is:
![[pe_ni_router_detailed.png]]