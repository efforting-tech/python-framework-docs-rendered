efforting.tech.conditions
=========================

.. py:module:: efforting.tech.conditions
	:synopsis: Conditions that can be used for filtering or constraining


.. py:class:: instance_of(type)

	Condition using isinstance(*item*, *type*)

	:param type type: Type to compare against

	.. py:attribute:: type

		Type to compare against

		:type: type


	.. py:method:: __call__(item)

		:return: Result of isinstance(*item*, *type*)
		:rtype: bool

