SYSTEM
^^^^^^^^
The ``SYSTEM`` component of a CASL model allows the user to define basics, initialization criteria, system wide functions, entity types and termination conditions.

Name
####################
This is the name of the CASL model and the name the generator gives to the Repast Simphony project as well as the file that controls the simulation. Any character is accepted. Blank names or names only with whitespace are not allowed.

Description
####################
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Ruleset
####################

- ``type``:
- ``inspection_level``:
- ``lenient_exceptions``: .. diversity modularity;
- ``semantic_groups``:
	This has controls if the model is a CASL or CASL-SG model. It takes two values, either ``enable`` or ``disable``. 
	To learn more about CASL-SG...

Parameters
####################
This stores the ``SYSTEM`` parameters. Some examples::

	var int:numberOfCells = 800;
	var string:UserConfigurationPath = "some/path/to/a/file";

Unlike entity parameters, the ``SYSTEM`` parameters are generated in the simulation initialization file with their assignments (if any) set as their default values.


Functions
####################

This stores the ``SYSTEM`` functions. 
An ``initialize`` function is required, otherwise the ``SYSTEM`` will not be able to start. For example::

	def initialize(var int:numAgents)(): {
		self.
	};

Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this SYSTEM
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this SYSTEM
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Agent_Types
####################
This is a list of all the agent types that will be in the model. For example::

	Pigeon,
	Eagle,
	Dove;

Environment_Types
####################
This is a list of all the environment types that will be in the model. For example::

	Road,
	Hospital,
	University,
	Business;

End_Conditions
####################
This stores a list of termination conditions that once met will cause the simulation to end. Typically, this will be a step number.
Example::

	condition STEPS terminationStep;