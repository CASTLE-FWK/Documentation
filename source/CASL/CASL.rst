CASL Documentation
==================================

.. toctree::
	:maxdepth: 2
   	:glob:
	
	Examples/*

.. contents::
	:depth: 2


Introduction
===============
Complex Adaptive Systems Language (CASL) is a declarative agent-based modeling language for create large scale and complicated complex adaptive systems models.

Publications featuring CASL
----------------------------
* `L. Birdsey, C. Szabo, K. Falkner: CASL: A Declarative Domain Specific Language For Modeling Complex Adaptive Systems, Winter Simulation Conference 2016 <https://scholar.google.com.au/scholar?cluster=12737184980596789335&hl=en&as_sdt=0,5>`_

How to use CASL
===============
- `Overview`_
- `CASL Structure`_
	- `System`_
	- `Agents`_
	- `Environments`_
- `CASL-SG`_
	- `Semantic Groups`_


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

Description
###############
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Parameters
##########

Functions
#########

Behaviors
##########

Interactions
#############

Adaptation
##########

Subsystems
###########



ENVIRONMENTS
^^^^^^^^^^^^

Description
###############
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Parameters
##########

Functions
#########

Behaviors
##########

Interactions
#############

Adaptation
##########

Subsystems
###########

CASL-SG
-------



SEMANTIC GROUPS
^^^^^^^^^^^^^^^


Examples
--------
Example CASL and CASL-SG models are located in the CASTLE-FWK Github page. However, here are some useful simple models with thorough descriptions.

- Game Of Life
- Flock of Birds
- Social Network



