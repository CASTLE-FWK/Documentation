Functions
=========

A function in CASL consists of ``def``, a function name, at least zero input parameters, and an optional single output parameter. An example is::

	def function(var bool:in)(var int:out): {		
		if (bool) then
			out = 10;
		else
			out = 3;
		endif;
	};

Return types are implicit in functions and only occur if a output variable is declared. If no output variable is declared, the function will not return anything.