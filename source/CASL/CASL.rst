CASL Documentation
==================================

.. contents::
	:depth: 3

.. toctree::
	:maxdepth: 2
   	:glob:
	:hidden:

	Blocks/*
	Examples/*

Introduction
------------
Complex Adaptive Systems Language (CASL) is a declarative agent-based modeling language for create large scale and complicated complex adaptive systems models.

A note: the term CASL by itself refers to both CASL and CASL-SG. CASL-SG only refers to the additional features of CASL-SG. In the case of a CASL (and not CASL-SG) description, it will be stated as such.


.. How to use CASL
.. ------------
.. - `Overview`_
.. - `CASL Structure`_
.. 	- `System`_
.. 	- `Agents`_
.. 	- `Environments`_
.. - `CASL-SG`_
.. 	- `Semantic Groups`_


Overview
--------
For CASL, each model consists of a single ``SYSTEM`` block, at least one ``AGENT`` block, and at least one ``ENVIRONMENT`` block.
The most basic CASL file looks like::

	SYSTEM: {
		name: "CASL EXAMPLE";
		description: "";
		ruleset: {
			type: lenient;
			inspection_level: none;
			lenient_exceptions: diversity modularity;
			semantic_groups: disable;
		};
		parameters: {};
		functions: {};
		agent_types: {
			anAgent;
		};
		environment_types: {
			anEnvironment;
		};
		end_conditions: {
			condition STEPS terminationStep;
		};	
	};

	AGENT anAgent: {
		description: "";
		parameters: {};
		functions: {};
		behaviors: {};
		interactions: {};
		adaptation: {};
		subsystems: {};
	};

	ENVIRONMENT anEnvironment: {
		description: "";
		environment_rules: {
			type: implicit
			attributes: virtual
			layout_type: BOUND;
		};
		parameters: {};
		functions: {};
		behaviors: {};
		interactions: {};
		adaptation: {};	
		subsystems: {};
		group_interactions: {};
	};




CASL Structure
--------------
The follwing section describes the functionality of each CASL component.

SYSTEM
^^^^^^^^^^^^
The ``SYSTEM`` component of a CASL model allows the user to define basics, initialization criteria, system wide functions, entity types and termination conditions.

Name
##########
This is the name of the CASL model and the name the generator gives to the Repast Simphony project as well as the file that controls the simulation. Any character is accepted. Blank names or names only with whitespace are not allowed.

Description
###############
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Ruleset
#########

- ``type``:
- ``inspection_level``:
- ``lenient_exceptions``: .. diversity modularity;
- ``semantic_groups``:
	This has controls if the model is a CASL or CASL-SG model. It takes two values, either ``enable`` or ``disable``. 
	To learn more about CASL-SG, click here `CASL-SG`_.

Parameters
###############

Functions
##########

Agent_Types
###############

Environment_Types
####################

End_Conditions
####################


AGENTS
^^^^^^
An Agent in CASL and CASL-SG has the following structure:: 

	AGENT theAgentsName: {
		description: "";
		parameters: {};
		functions: {};
		behaviors: {};
		interactions: {};
		adaptation: {};
		subsystems: {};
	};

An ``AGENT`` block starts of with ``AGENT`` and the agents name

Description
###############
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Parameters
###########
This stores the ``AGENT`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
#########
This stores the ``AGENT`` functions. Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this AGENT
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this AGENT
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
##########
This stores the ``AGENT`` behaviors. An example::

	changeStateToDead[SELF][DELAYED](): {
		FUNCTION.setState(false);
	};


:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
#############



:doc:`More about Interactions <Blocks/Interactions>`

Adaptation
##########


:doc:`More about Adaptations <Blocks/Adaptations>`

Subsystems
###########


:doc:`More about Subsystems <Blocks/Subsystems>`



ENVIRONMENTS
^^^^^^^^^^^^

Description
###############
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Parameters
###########
This stores the ``AGENT`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
#########
This stores the ``AGENT`` functions. Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this AGENT
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this AGENT
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
##########



:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
#############



:doc:`More about Interactions <Blocks/Interactions>`

Adaptation
##########


:doc:`More about Adaptations <Blocks/Adaptations>`

Subsystems
###########


:doc:`More about Subsystems <Blocks/Subsystems>`

CASL-SG
-------



SEMANTIC GROUPS
^^^^^^^^^^^^^^^

Parameters
###########
This stores the ``AGENT`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
#########
This stores the ``AGENT`` functions. Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this AGENT
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this AGENT
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
##########



:doc:`More about Behaviors <Blocks/Behaviors>`

GROUP_TRANSFER
###############





Examples
--------
Example CASL and CASL-SG models are located in the CASTLE-FWK Github page. However, here are some useful simple models with thorough descriptions.

- Game Of Life
- Flock of Birds
- Social Network



