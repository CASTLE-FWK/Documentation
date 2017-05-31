Getting Started
^^^^^^^^^^^^^^^^^

To get started using CASL and CASTLE there are a few things that need to be done:

Dependencies
#############
	`Repast Simphony <repast.github.io>`_
	MongoDB (optional)
	XText (this can be resolved automatically by Eclipse)

Installation
##############
	1) Download and install Repast Simphony
	2) Add http://download.eclipse.org/modeling/tmf/xtext/updates/composite/releases/ to ``Available Software Sites`` in Repast
	3) Update Repast (Eclipse Neon.3 is the minimum version required)
	4) Clone the CASTLE distribution `repository <https://github.com/CASTLE-FWK/CASTLE>`_ to somewhere useful
	5) In Repast::

		Help -> Install New Software -> Add... -> 
		Archive... "Point to CASL.zip in the cloned repository" 

	Install, and wait for the remaining dependencies to be resolved.

Usage
#########
Using CASL to creating simulation code for use in Repast Simphony requires 2 stages, firstly, creating the model and generating the code. Secondly, moving the code into a Repast Simphony project:

	1) Create your CASL project. Currently, this is just an Eclipse general project.
	2) Create your ``.casl`` file
	3) Clone the ``commons.casl`` file located `here <https://github.com/CASTLE-FWK/Models>`_ into the project. This is also currently required.

When you create a CASL model file and save, code generated for use in Repast will be located in a directory called ``src-gen``. To use this in Repast you must:
	1) Create a Repast Simphony Project with the same name as your CASL project.
	2) Copy and paste the directories and files located in ``src-gen`` into the Repast project. This includes the MODEL_NAME.rs directory. (This step will soon be unnecessary) 
	3) Follow the guides on how to setup a Repast simulation located at the main `Repast site <repast.github.io>`_
