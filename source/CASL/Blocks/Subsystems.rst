Subsystems
^^^^^^^^^^

Subsystems allow for one or more ``AGENT`` entities to exist and operate inside another ``AGENT``. This is also extended to the ``ENVIRONMENT`` entity.
Subsystems are simply declared as an ``AGENT`` or ``ENVIRONMENT`` depending on the parent type. An example for a subagent is as follows::

	//Other parent agent sections
	subsystems: {
		AGENT subAgent: {
			description: "";
			parameters: {};
			functions: {};
			behaviors: {};
			interactions: {};
			adaptation: {};
			subsystems: {};
		};
	};

These subentities can interact with other subentities in the same parent entity, and the parent entity can interact with their own subentities. Subentities are not allowed to interact with subentities from other entities, unless through an interaction of the parent entity.

Examples
########