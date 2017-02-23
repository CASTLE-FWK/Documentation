CASL-SG
============

The large scale extension to CASL introduces a new entity type called ``GROUP``

Overview 
-------------------
A generic CASL-SG model example is below::

	import cas.test.commons.*;

	SYSTEM: {
		name: "CASL-SG EXAMPLE";
		description: "";
		ruleset: {
			type: lenient;
			inspection_level: none;
			lenient_exceptions: diversity modularity;
			semantic_groups: enable;
		};
		parameters: {};
		functions: {};
		agent_types: {
			anAgent;
		};
		group_types: {
			aGroup;
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


	GROUP aGroup: {
		description: "";
		group_rules: {
			layout_type: BOUND;
		};
		parameters: {};
		functions: {};
		behaviors: {};
		transmissions: {};
		internals: {};
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


Aside from the extra entity, there are few changes. The ``ENVIRONMENT`` gains a new component called ``group_interactions``.