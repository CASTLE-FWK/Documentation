CASL Basics
----------------

The Language
^^^^^^^^^^^^^^
CASL supports common declarative language constructs such as ``if/else`` statments, loops, recursion, etc.

Naming Rules & Conventions
############################

Naming rules in CASL are the same as in Java. These are:

* All variable and entity names must start with an alphabetic character

* 


Reserved Keywords
##################

There are several reserved keywords in CASL, they are as follows::

	if
	else
	then
	var
	agt
	grp
	env
	for
	foreach
	endif
	endfor


Declaration and Assignment
###########################
Variable declarations must be prefaced with ``var``, for example::
	
	var int:anInteger = 39;
	var Vector2:aVector;
	var List<Item>:itemList;

However, if you wish to store references to entities you must use ``agt``, ``grp``, or ``env`` for Agents, Groups, and Environments respectively. For example::

	agt Cell:aCell;
	grp Room:myRoom;
	env Forest:theForest;


Types
############
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
#############
``IF`` statments in CASL are similar to C and Java based languages. An example is::

	if (condition) then
		//do something
	else if (another condition) then
		//do something else
	else
		//do something else
	endif;

Loops
#############
CASL supports ``for`` and ``foreach`` loops. These mostly follow Java conventions, with a couple of exceptions. For example::

	//For-loop incrementer must be of form x = x + k (until issue is resolved)
	for (var int:i = 0; i < 10; i = i +1) do
		//Do something
	endfor

	foreach (Item item : ItemList) do
		//Do something
	endfor


Self Reference
##########################
To reference a parameter in the same entity, the ``self`` keyword must be used. For example::
	
	var int:newNum = self.oldNum * 2;

``self`` behaves similarly to the ``this`` keyword in Java. However, when referencing parameters from the same entity, the ``self`` keyword must be used. The CASL editor will warn you if this is not done.


Component Reference
##########################
These are::

	FUNCTION.functionName();
	BEHAVIOR.behaviorName();
	INTERACTION.interactionName();
	AGT_INTERACTION.interactionName();
	ENV_INTERACTION.interactionName();
	GRP_TRANSMISSION.transmissionName();
	ADAPTATION.adaptationName();


.. TODO: Special component references

