### Preserving Digital Art And Games For 100 Years!

_wilkie_

Wilkie works as something like a digital archivest. In particular, he helps scientists package their code and methods in a way that is reproducable and storable for the long term, so that future scientists can re-run the experiments if they need to. However, it's really hard to get people to care about archival.

This is surprising. In the physical world, we can walk up to paintings that are hundreds of years old. You can go to France and see the Mona Lisa. But in the digital world, you can't even compile code that you write before you left on your trip.

When growing up, Wilkie was mezmorized by a game called ZZT in which you play as a disembodied head that walks around doing things in a 2D world. How would we archive this as a form of interactive media? It's an interactive game, so we when we archive it we have to preserve that interactivity.

Normally when archiving software, we virtualize or emulate the dependencies of the executable and call it a day. But what happens if KDM stops being maintained? What happens if the version of VirtualBox you need stops being mainted?

Moreover, is it enough to just archive the game? In the case of ZZT, packaged with the game was a level editor, which the community has embraced in full. It's not enough to archive ZZT.

We can do something more containerey:
* ZZT specifies it needs DOS
* DOS can run in DOS box, which specifies its own dependencies
* DOS box is packaged with Docker, but could be any containerization solution

We can also add more depdencies like a windowing manager.

As a takeaway, when building tools, think about how you're hurting or helping people archive what they make in the long run.
