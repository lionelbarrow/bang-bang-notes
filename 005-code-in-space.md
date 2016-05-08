### Code in Spaaace!

_Katie Bechtold_

Katie has worked on a lot of software that has gone to other planets or at least flown past them.

A spacecraft is a lot like a network of embedded computers. Different computer functions might be:

* Command and data handling
* Fault protection
* Scientific intruments
* Power distribution
* Guidance and control

Most of them have to worry about the following problems.

* Space is big -> spacecraft have to go far away -> access to hardware is remote with big time lags
  -> spacecraft needs to operate independently
  * 5 hours to New Horizons (Pluto), 15 hours to Voyager
* Earth is a gravity well -> space is expensive to get to (11.2 kilometers per second escape speed)
  -> spacecraft cost a lot of money -> $10-25k per kilogram of equipment in space -> most missions
  are a few hundred million to a few billion dollars -> missions are rare -> risk aversion
* Therefore, need spacecraft to be very very reliable and predictable:
  * Real time operating systems. These are predictable, not fast. Need predictable timing for things like firing thrusters, measuring things, shielding electronics from the sun.
  * Deterministic languages and tools. Deterministic means not using dynamic memory allocation, period. Also avoid recursion. Loops must have statically inferrable termination times. Languages used: C, Ada, Forth.
  * Totally scheduled data bus periods; no random retrys on ethernet cables between systems. More modern spacecraft networks are full point to point duplex networks, so no congestion is possible.
* If far from the sun, can't use solar power. NASA currently low on plutonium. 
* Need lots of radiation shielding. High energy particles, however, don't care about your shielding.
  * 3 bits for every 1 bit in memory which vote
  * Watch dog timers on processes.
  * Leads to older hardware! More constraints for programmers like "12 MHz processor" and "70 KB main memory"
