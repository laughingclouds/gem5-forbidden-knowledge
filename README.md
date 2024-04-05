# gem5 forbidden knowledge

An amateurs thoughts and documentation on Gem5 source code.

Open in [Obsidian](https://obsidian.md/) for the image embeds to work.

**Why?**
As more than just a simulator but a ["simulator platform"](https://www.gem5.org/documentation/learning_gem5/introduction/#what-is-gem5) gem5 requires you to add "new capabilities" to work on "novel" ideas. Naturally, that means making changes to the source code of gem5 itself.
Sadly not many tutorials/guides exist that would explain the source. There is [one](https://github.com/cirosantilli/linux-kernel-module-cheat) by [Ciro Santilli](https://cirosantilli.com/) but he has stopped working on it.


My attempt will be to document code behaviour of the [stable branch](https://github.com/gem5/gem5/tree/stable) of the gem5 source code. I will try to relate the code with Computer Architecture theory wherever and whenever I can.


> As previously stated, this is an amateurs documentation. The language used will not be the most technically accurate and might even be wrong. I will make all the effort possible to keep things as accurate as possible but I'm not making any promises. This is a hobby project after all.

*This project is more for me than for others but contributions and discussions are more than welcome.*

**Relevant:**

- [Gem5 boot camp from 2020](https://gem5bootcamp.github.io/gem5-bootcamp-env/modules/introduction/index/)
- [Assignments on Gem5](https://tusharkrishna.ece.gatech.edu/teaching/garnet_gt/) - Georgia Tech

# Existing research work

I couldn't find many examples online that included making changes to the gem5 source code itself. But the ones I did find are a delight to look at. Here they are:

- [BINDU](https://github.com/noc-deadlock/bindu): Deadlock-Freedom with One Bubble in the Network
- [DRAIN](https://github.com/noc-deadlock/drain): Deadlock Removal for Arbitrary Irregular Networks
- [BBR](https://github.com/noc-deadlock/bbr): Brownian Bubble Router
- Everything in this [gh org](https://github.com/noc-deadlock) really.

# References

- [Learning gem5](https://www.gem5.org/documentation/learning_gem5/introduction/) by Jason Lowe-Power
- [Ruby](https://www.gem5.org/documentation/general_docs/ruby/): memory system
	- [garnet](https://www.gem5.org/documentation/general_docs/ruby/garnet-2/): interconnection network model