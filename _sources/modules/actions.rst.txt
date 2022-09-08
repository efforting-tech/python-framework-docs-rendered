efforting.tech.actions
======================

.. py:module:: efforting.tech.actions
	:synopsis: Commonly taken actions

.. py:decorator:: instantiate(cls)

	:param type cls: Class to instantiate
	:return: Instantiated class
	:rtype: object

.. py:class:: return_value(value)

	Returns *value* when called.

	.. py:attribute:: value

		The value to return

		:type: object

	.. py:method:: __call__()

		:return: *value*
		:rtype: object

