efforting.tech.symbols
======================


.. py:module:: efforting.tech.symbols
	:synopsis: Data types for dealing with symbolic identities

.. py:data:: CALLING_MODULE

	:type: ~efforting.tech.symbols.symbol
	:value: symbol('CALLING_MODULE')

.. py:class:: symbol(name=None, bool_state=None, owner=CALLING_MODULE)

	:param str name: Identity of the symbol
	:param bool_state: Identity of the symbol
	:type bool_state: bool or None
	:param owner: Owner of the symbol for being able to refer to it canonically
	:type owner: ~efforting.tech.symbols.symbol

	.. py:attribute:: name

		:type: str

	.. py:attribute:: bool_state

		:type: bool or None


	.. py:method:: __get_state__()

	.. py:method:: __set_state__(state)

	.. py:method:: __set_name__(target, name)

	.. py:method:: __bool__()

	.. py:method:: __repr__()

.. py:class:: symbol_group_type()

	.. py:method:: __repr__()

	.. py:method:: __dir__()

.. py:class:: symbol_group()

	.. py:classmethod:: __init_subclass__()
