efforting.tech.runtime_utils
============================

.. py:module:: efforting.tech.runtime_utils
	:synopsis: Various utilities for runtime operations

.. py:data:: _recursion_tracker

	:type: ~efforting.tech.counting.counter
	:value: counter()

.. py:class:: recursion_limit(limit)

	:param int limit: Maximum recursion limit

	.. py:attribute:: limit

		Maximum recursion limit

		:type: int

	.. py:attribute:: recursion_key

		Key used for the counter for the recursion limit.
		The key is created from frame.f_code and frame.f_lineno from the frame that called __init__.

		:type: tuple
		:value: (frame.f_code, frame.f_lineno)


	.. py:method:: __enter__()

		Increments the counter for recursion_key

		:rtype: None
		:raises RecursionError: if the counter surpasses limit for the recursion_key.

	.. py:method:: __exit__(et, ev, tb)

		Decrements the counter for recursion_key

		:param type et: Exception type for any pending exception
		:param BaseException ev: Exception value for any pending exception
		:param tb: Traceback object for any pending exception
		:type tb: types.TracebackType
		:rtype: None


.. py:class:: forward_declared_instance

	This is used to hold a reference for an instance that will later get its __class__ swapped out.
	The usecase for this is to be able to refer to things that does not yet exist as illustrated by :data:`~efforting.tech.symbols.CALLING_MODULE`


.. py:class:: forward_declared_type

	This is used to hold a reference for a type that will later get its __class__ swapped out.

	.. py:attribute:: __init__

		..
			Not sure how to document a function that is using a singleton like this.

		:value: ~efforting.tech.actions.ignore_call

.. py:function:: upgrade_forward_declared_item(target, source)

	:param object target: Target that is being manipulated
	:param object source: Source for copying __class__ and state

	The state is transferred by calling target.__set_state__(source.__get_state__())

	..
		Figure out inline highlighted code