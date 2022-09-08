efforting.tech.counting
=======================

.. py:module:: efforting.tech.counting
	:synopsis: Utilities for counting things


.. py:class:: counter

	.. py:attribute:: _state

		Dictionary of the current count

		:type: dict
		:value: dict()

		.. note::

			It is not recommended to manipulate this attribute directly

	.. py:attribute:: _lock

		Lock for when incrementing or decrementing the counter

		:type: threading.Lock
		:value: threading.Lock()

		.. note::

			It is not recommended to manipulate this attribute directly

	.. py:method:: __getitem__(key)

		:return: The counting value of key or 0 if not defined
		:rtype: int or float

	.. py:method:: increment(key, amount=1)

		Increment the counter for the key *key*

		:param object key: Identity used as key
		:param amount: Amount to increment counting value by
		:type amount: int or float
		:return: The counting value for *key* after incrementing
		:rtype: int or float

	.. py:method:: decrement(key, amount=1)

		Decrement the counter for the key *key*

		:param object key: Identity used as key
		:param amount: Amount to decrement counting value by
		:type amount: int or float
		:return: The counting value for *key* after decrementing
		:rtype: int or float





