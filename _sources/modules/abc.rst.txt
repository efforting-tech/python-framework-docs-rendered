efforting.tech.abc
==================

.. role:: python(code)
   :language: python

.. py:module:: efforting.tech.abc
	:synopsis: Abstract Base Class system

.. py:data:: _abc_directory
	:type: ~efforting.tech.data_directory.generic_data_directory
	:value: generic_data_directory()

.. py:data:: _abc_registry
	:type: dict
	:value: dict()

.. py:data:: abc
	:type: ~efforting.tech.data_directory.generic_data_directory_accessor
	:value: _abc_directory.root_accessor

	This object can be used to access canonical :term:`abc` s such as the fictive example :python:`abc.data.text.unicode`.

.. seealso:: :doc:`../examples/abc_basics`

.. py:function:: create_abc(path):

	:param path: Path of :term:`abc` to create and register
	:type path: str or ~pathlib.PurePath
	:rtype: abc_type
	:returns: New instance of :class:`abc_type`

	Creates and registers an :term:`abc` based on a canonical path.

.. py:class:: abc_type(name, bases, scope)

	:param str name: Name of the :term:`abc` type
	:param bases: Bases for the new :class:`abc_type`
	:type bases: tuple of :class:`abc_type`

	.. warning::

		This class can be created in two very different manners depending on whether bases is set or not.
		If there are no bases the returned class will be an :term:`abc` but if bases are specified the assumption is that a :term:`concrete class` is to be created.
		When creating a :term:`concrete class` there will be a complex machinery in place to assist with a plethora of features related to this.

		These features are still in development and as they progress this message will be updated to be less vague.

	.. py:method:: __getattr__(name)

		Retrieve a base class by name relative to the current one from the :data:`_abc_directory`.
		If the current :class:`abc_type` is :code:`path.to.thing` and name is `item` the :class:`abc_type` for :code:`path.to.thing.item` is returned.

		:raises AttributeError: if there is such class in the :data:`_abc_directory`.
		:rtype: abc_type

	.. py:method:: __repr__()

		The format of :class:`abc_type` is :python:`f'_abc_directory[{str(self._path)!r}]'` for example :code:`_abc_directory['path.to.thing']`.

		:rtype: str

	.. py:method:: __instancecheck__(instance)

		:param object instance: An instance - possibly registered as a :term:`concrete class` of some :term:`ABC`.

		First the bases of :python:`instance.__class__` is looked up in the :data:`_abc_registry`.
		Then the :class:`~efforting.tech.data_path.data_path` of the current :class:`abc_type` is walked and for each subsequent :class:`~efforting.tech.data_path.data_path` (including the initial one) it is checked whether that candidate is one of the bases.
		If that is the case :python:`True` is returned.
		If no such case is identified, then :python:`False` is returned.

		The purpose of this is to separate this :term:`ABC` system from the Python built in one.

		:rtype: bool


	.. py:method:: __subclasscheck__(subclass)

		:param type subclass: A type - possibly registered as a :term:`concrete class` of some :term:`ABC`.


		First the bases of :python:`subclass` is looked up in the :data:`_abc_registry`.
		Then the :class:`~efforting.tech.data_path.data_path` of the current :class:`abc_type` is walked and for each subsequent :class:`~efforting.tech.data_path.data_path` (including the initial one) it is checked whether that candidate is one of the bases.
		If that is the case :python:`True` is returned.
		If no such case is identified, then :python:`False` is returned.

		The purpose of this is to separate this :term:`ABC` system from the Python built in one.

		:rtype: bool
