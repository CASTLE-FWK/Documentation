Behaviors
^^^^^^^^^^

The primary driver of all entities in CASL.


Structure
##########
A behavior in CASL consists of a name, contact type, trigger type, and input parameters. Two simple examples::

	//Generic
	behaviorName[SELF][INSTANT](input parameters): {
		//Do something
	};

	//Occur each step
	behave[SELF][REPEAT (1)](): {
		//Do something
	};

Contact Types
####################

There are 2 contact types, namely, ``SELF``, and ``AFFECT``

* ``SELF``:

* ``AFFECT``:

If you select the wrong type, the CASL Editor will warn you and prevent your model code from generating.

Trigger Types
####################

There are 4 trigger types, namely, ``INSTANT``, ``DELAYED``, ``STEP``, ``REPEAT``.

* ``INSTANT``:
	This triggers the behavior as soon as it is called.

* ``DELAYED``:
	This delays the triggering of the behavior until the :doc:`CLEANUP </CASL/BasicCASL>` phase of the same step.

* ``STEP (x)``:
	This triggers the behavior after ``x`` steps, where ``x`` is greater than 0.

* ``REPEAT (x)``:
	This causes the behavior to occur every ``x`` steps, where ``x`` is greater than 0.


Input Parameters
##############################
Any input parameter is allowed.



Examples
####################
::

	//Every step, interact with neighbors
	doStep[AFFECT][REPEAT(1)](): {
		INTERACTION.checkNeighbors();
	}
