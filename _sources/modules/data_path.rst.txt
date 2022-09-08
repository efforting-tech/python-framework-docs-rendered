efforting.tech.data_path
========================


.. py:module:: efforting.tech.data_path
	:synopsis: Data types useful for representing canonical paths



.. py:class:: _data_path_flavour

	.. py:data:: sep

		:type: str
		:value: '.'

	.. py:data:: altsep

		:type: str
		:value: ''

	.. py:data:: has_drv

		:type: bool
		:value: False


	.. py:function:: splitroot(part, sep=sep)

	.. py:function:: casefold(s)

	.. py:function:: casefold_parts(parts)

	.. py:function:: compile_pattern(pattern)

	.. py:function:: is_reserved(parts)


.. py:class:: data_path

	.. py:data:: _flavour

		:type: _data_path_flavour
		:value: _data_path_flavour()

	.. py:data:: __slots__

		:type: tuple
		:value: ()

	.. py:function:: __repr__()
