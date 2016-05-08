### Plants are Recursive - Using L Systems to Generate Weeds

_Sher Minn Chong_

Recursion not just in the sense of functions calling themselves, but rather the self-similar repetition (e.g. fractals). Many plants exhibit obvious fractal tendencies.

L-systems: string re-writing sytem that consists of axions are rules.

For example:

Axiom: A
Rules: A -> AB
       B -> A

Iteratively apply rules on the starting state to create an L-system.

How to go from string and symbols to drawing?

Use strings to represent a given drawing transformation such as "rotate 60 degrees" or "add edge"

To draw snowflake:

Axiom: F
Rules: F -> F - F  + F - F

Where F is a line, and -/+ represent rotations.

So, we can use this to describe plants, with some modifications. We introduce [ and ] to save and restore state. Can also introduce several transformation rules for the same symbol and randomly choose between them.
