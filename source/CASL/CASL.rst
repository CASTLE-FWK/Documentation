CASL
==========

Introduction
------------
Complex Adaptive Systems Language (CASL) is a declarative agent-based modeling language for create large scale and complicated complex adaptive systems models.

A note: the term CASL by itself refers to both CASL and CASL-SG. CASL-SG only refers to the additional features of CASL-SG. In the case of a CASL (and not CASL-SG) description, it will be stated as such.

Overview
--------
For CASL, each model consists of a single ``SYSTEM`` block, at least one ``AGENT`` block, and at least one ``ENVIRONMENT`` block.
The most basic CASL file looks like::

	import cas.test.commons.*;
	SYSTEM: {
		name: "CASL EXAMPLE";
		description: "";
		ruleset: {
			type: lenient;
			inspection_level: none;
			lenient_exceptions: diversity modularity adaptation; //This is current inactive
			semantic_groups: disable;
		};
		parameters: {
			var * int:terminationStep = 1000;
		};
		functions: {};
		agent_types: {
			anAgent;
		};
		group_types: {
			;
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
		functions: {
			def initialize()(): {};
		};
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
		parameters: {
			var LayoutParameters:layoutParameters;
		};
		functions: {
			def initialize()(): {};
		};
		behaviors: {};
		interactions: {};
		adaptation: {};	
		subsystems: {};
		group_interactions: {}; //This will soon not be necessary
	};

.. include:: BasicCASL.rst

Model Structure
-----------------
The follwing section describes the functionality of each CASL component.
A visual representation of the hierarchical structure of CASL is below **MAKE IMAGE**

.. include:: System.rst

.. include:: Agent.rst

.. include:: Environment.rst

.. include:: Group.rst

CASL Components
---------------
.. include:: Blocks/Parameters.rst
.. include:: Blocks/Functions.rst
.. include:: Blocks/Behaviors.rst
.. include:: Blocks/Interactions.rst
.. include:: Blocks/Adaptations.rst
.. include:: Blocks/Subsystems.rst

.. include:: SystemCalls.rst
.. include:: Macros.rst

