CASL Basics
===========

CASL Structure
--------------



The Language
-------------
CASL supports common declarative language constructs such as ``if/else`` statments, loops, recursion, etc.


Assignments
^^^^^^^^^^^^

Types
^^^^^^^^^^^^
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


``IF/ELSE``
^^^^^^^^^^^^
``IF`` statments in CASL are similar to C and Java based languages. An example is::

	if (condition) then
		//do something
	else if (another condition) then
		//do something else
	else
		//do something else
	endif;

Loops
^^^^^^^^^^^^

Self Reference
^^^^^^^^^^^^^^^^
To reference a parameter in the same entity, the ``self`` keyword must be used. For example::
	
	var int:newNum = self.oldNum * 2;

``self`` behaves similarly to the ``this`` keyword in Java. However, when referencing parameters from the same entity, the ``self`` keyword must be used. The CASL editor will warn you if this is not done.


Component Reference
^^^^^^^^^^^^^^^^^^^^^^
These are::

	FUNCTION.functionName();
	BEHAVIOR.behaviorName();
	INTERACTION.interactionName();
	ADAPTATION.adaptationName();

TODO: Special component references