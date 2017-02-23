Parameters
^^^^^^^^^^^


Structure
#########
A parameter in CASL consists of a descriptor, type, name, and optional assignment.
Generic parameter structure::

	descriptor type:name = assignment;

A descriptor can be either ``var``, ``agt``, ``grp``, or ``env``, which refers to a variable, ``AGENT``, ``GROUP``, or ``ENVIRONMENT`` respectively.

Types
######

Types can either be primitives or non-primitives. Example::

	var int:aNumber = 19; //A primitive
	var Vector2:aVector; //A non-primitive
	var Grid<agt.Cell>; //A paramaterized non-primitive

As Paramater Values
####################