Getting Started
^^^^^^^^^^^^^^^^^

To get started using CASL and CASTLE there are a few things that need to be done:

Dependencies
#############
	* `Repast Simphony <repast.github.io>`_

	* MongoDB (optional)

	* XText (this can be resolved automatically by Eclipse)

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
As CASL is in constant development, please make sure you have the current version of the plugin and ``CASTLE`` library. Simply ``git pull`` the cloned repo. Once you load Repast Simphony, selection Check For Updates from the Help menu, and it will look for the updated CASL plugin to update.


Using CASL to creating simulation code for use in Repast Simphony requires 2 stages, firstly, creating the model and generating the code. Secondly, moving the code into a Repast Simphony project:

	1) Create your CASL project. Currently, this is just an Eclipse general project.
	2) Create your ``.casl`` file. There are some templates located `here <https://github.com/CASTLE-FWK/Models>`_.
	3) Clone the ``commons.casl`` file located `here <https://github.com/CASTLE-FWK/Models>`_ into the project. This is also currently required for every CASL project.

When you create a CASL model file and save, code generated for use in Repast will be located in a directory called ``src-gen`` inside your CASL project directory. To use this in Repast you must:
	1) Create a Repast Simphony project with the same name as your CASL project.
	2) Copy and paste the directories and files located in ``src-gen`` into the Repast project. Copy and paste the file ``MODEL_NAME.rs`` file from ``src-gen`` to the Repast Simphony project's ``MODEL_NAME.rs`` directory. Allow for replacement.
	3) Add ``CASTLE.jar`` to the project's build path.
	4) Before running, select ``MODEL_NAME Model`` from the Run Configuration menu and add the ``CASTLE.jar`` to the build path of the project.
	5) To run, select ``MODEL_NAME Model`` from the Run menu. This will load the Repast Simphony simulator. Right-click ``Data Loaders`` and select ``Set Data Loader``. Select ``Custom ContextBuilder Implementation`` and this should automatically select the main CASL generated System class. Click next and then finish.
	6) To inspect and/or change the simulation parameters, you can click the parameters tab in Repast Simphony.
	7) When you are ready to execute the simulation, press the Play button near the top of the window.

	For more information, follow the guides on how to setup a Repast simulation located at the main `Repast site <repast.github.io>`_
