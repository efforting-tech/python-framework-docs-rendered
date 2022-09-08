efforting.tech.iter_utils
=========================

.. py:module:: efforting.tech.iter_utils
	:synopsis: Various utilities for iteration of data


.. py:function:: iter_public_items(source)

	:param object source: Source for iterating the public items in

	If source is of the type collections.abc.Mapping source.items() will be used as the source, otherwise source.__dict__.items() will be used.
	An item is considered public if its key does not begin with underscore.

	After filtering tuples of (key, value) are yielded.

	..
		Make sure things like type is not highlighted as a type when not intended as it.
		Figure out how to put inline source in the text.

.. py:function:: iter_public_values(source)

	:param object source: Source for iterating the public values in

	If source is of the type collections.abc.Mapping source.items() will be used as the source, otherwise source.__dict__.items() will be used.
	An item is considered public if its key does not begin with underscore.

	After filtering the items, values are yielded.

	..
		Make sure things like type is not highlighted as a type when not intended as it.
		Figure out how to put inline source in the text.