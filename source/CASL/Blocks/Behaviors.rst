Behaviors
=========

The primary driver of all entities in CASL.


Structure
---------
A behavior in CASL consists of a name, contact type, trigger type, and input parameters. Two simple examples::

	//Generic
	behaviorName[SELF][INSTANT](var int:num): {
		//Do something
	};

	//Occur each step
	behave[SELF][REPEAT (1)](): {
		//Do something
	};

Contact Types
-------------

There are 2 contact types, namely, ``SELF``, ``ENVIRONMENT``, and ``AGENT``.

* ``SELF``:

* ``ENVIRONMENT``:

* ``AGENT``:

Trigger Types
--------------

There are 4 trigger types, namely, ``INSTANT``, ``DELAYED``, ``STEP``, ``REPEAT``.

* ``INSTANT``:
	This triggers the behavior as soon as it is called.

* ``DELAYED``:
	This delays the triggering of the behavior until the :doc:`CLEANUP </CASL/BasicCASL>` phase of the same step.

* ``STEP (x)``:
	This triggers the behavior after ``x`` steps, where ``x`` is greater than 0. If no ``x`` value is defined, it triggers the behavior in the next step.

* ``REPEAT (x)``:
	This causes the behavior to occur every ``x`` steps. 


Input Parameters
-----------------



Examples
---------