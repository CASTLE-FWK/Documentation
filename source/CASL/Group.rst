SEMANTIC GROUP
---------------

A semantic group in CASL-SG has the following structure::

	GROUP aGroup: {
			description: "";
			group_rules: {
				layout_type: BOUND;
			};
			parameters: {
				var LayoutParameters:layoutParameters;
			};
			functions: {
				def initialize()(): {};
			};
			behaviors: {};
			external_interactions: {};
			internal_interactions: {};
	};


Parameters
^^^^^^^^^^^
This stores the ``GROUP`` parameters.

:doc:`More about Parameters <Blocks/Parameters>`

An ``GROUP`` must have the ``layoutParameter`` variable. In addition, a layout representation variable must be declared that matches the ``layout_type``. For example, if the ``layout_type`` is set to ``GRID``::

	var Grid<Cell>:cellGrid;

Functions
^^^^^^^^^
This stores the ``GROUP`` functions. Each ``GROUP`` requires an ``initialize`` function to be declared and the CASL Editor will warn you if it is missing. 

:doc:`More about Functions <Blocks/Functions>`

Behaviors
^^^^^^^^^^
This stores the ``GROUP`` behaviors. 

:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
^^^^^^^^^^^^^
This stores the ``GROUP`` interactions. An example::

	checkNeighboursVelocity[GROUP][INSTANT](): {
		BEHAVIOR.adjustVelocity(neighbour.AGT_INTERACTION.getVelocity());
	};


:doc:`More about Interactions <Blocks/Interactions>`

External_Interactions
^^^^^^^^^^^^^^^^^^^^^^^

Internal_Interactions
^^^^^^^^^^^^^^^^^^^^^^^