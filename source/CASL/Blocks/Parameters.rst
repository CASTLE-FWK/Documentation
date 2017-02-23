Parameters
==========

A parameter in CASL consists of a descriptor, type, name, and optional assignment.
Generic parameter structure::

	descriptor type:name = assignment;

A ``descriptor`` can be either ``var``, ``agt``, ``grp``, or ``env``, which refers to a variable, ``AGENT``, ``GROUP``, or ``ENVIRONMENT`` respectively.

Types
--------------
A variable in CASL consists of either primitive or non-primitive types. The primitive types are::

	bool
	int
	string
	float
	null

Non-primitive types in CASL are defined in ``.casl`` library files. By default, CASL comes with::

	Vector2<descriptor: type>
	List<descriptor: type>
	Queue<descriptor: type>
	PQueue<descriptor: type>
	Neighbors<descriptor: type>
	LayoutParameters<descriptor: type>
	Grid<descriptor: type>