efforting.tech.filter_utils
===========================

..
	There is lots of improvements to be done here.
	Properly document data types, provide examples and so on.

.. py:module:: efforting.tech.filter_utils
	:synopsis: Various utilities for filtering data


.. py:class:: item_filter(condition=None)

	.. note::
		This class might be renamed since it is not very clear it is intended for sequences

	:param condition: Callable condition used for filtering elements in a sequence
	:type condition: callable or None

	.. py:attribute:: condition

		Callable condition used for checking items

		:type: callable or None

	.. py:method:: __call__(source)

.. py:class:: dict_item_filter(key=None, value=None, key_condition=None, value_condition=None)


	.. note::
		This class might be renamed since it is not very clear it is intended for sequences of (key, value)-tuples.
		Also this class does more than filtering, it can also process the keys and values.

	:param key: Callable used to process keys in items before returning them.
	:type key: callable or None

	:param value: Callable used to process values in items before returning them.
	:type value: callable or None

	:param key_condition: Callable condition used for filtering items based on their key.
	:type key_condition: callable or None

	:param value_condition: Callable condition used for filtering items based on their value.
	:type value_condition: callable or None

	.. py:attribute:: key

		Callable used to process keys in items before returning them.

		:type: callable or None

	.. py:attribute:: value

		Callable used to process values in items before returning them.

		:type: callable or None


	.. py:attribute:: key_condition

		Callable condition used for filtering items based on their key

		:type: callable or None


	.. py:attribute:: value_condition

		Callable condition used for filtering items based on their value

		:type: callable or None

	.. py:method:: __call__(source)

		Observe that filtering is done on the unprocessed keys and values even if key and/or value is set.

