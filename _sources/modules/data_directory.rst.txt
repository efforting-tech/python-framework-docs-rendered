efforting.tech.data_directory
=============================


.. py:module:: efforting.tech.data_directory
	:synopsis: Data types useful for storing canonical data



.. py:class:: generic_data_directory

	.. py:data:: path_type

		:type: type
		:value: efforting.tech.data_path.data_path

	.. py:function:: __init__(self, name=None, value=UNDEFINED, children=None, parent=None, lazy_loader=None)

	.. py:function:: __setitem__(self, key, value)

	.. py:function:: __getitem__(self, key)

	.. py:function:: update(self, other)

	.. py:function:: cast_path(self, path)

	.. py:function:: get_directory(self, key, default=ACTION.RAISE_EXCEPTION)

	.. py:property:: path(self)

	.. py:property:: root(self)

	.. py:function:: get_or_create_child_entry(self, name)

	.. py:function:: get_or_create_value(self, path, factory)

	.. py:function:: create_value(self, path, factory)

	.. py:function:: walk_depth_first(self, include_undefined=True)

	.. py:function:: walk_bredth_first(self, include_undefined=True)

	.. py:function:: to_dict(self, include_undefined=False)

	.. py:function:: create_attribute_based_registration_decorator(self, attribute)

	.. py:property:: register(self)

	.. py:data:: walk

		:value: walk_bredth_first

.. py:class:: path_data_directory

	.. py:data:: path_type

		:value: Path

.. py:class:: pure_posix_path_data_directory

	.. py:data:: path_type

		:value: PurePosixPath

.. py:class:: pure_windows_path_data_directory

	.. py:data:: path_type

		:value: PureWindowsPath
