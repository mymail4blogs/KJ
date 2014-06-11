Resource
========

Resource will be used to fetch the results it has a reference to Node.

Methods
---------------
Following  functionality provided by Resource::

    public T getNode();
    public Space<?> getSpace();
    public Promise<List<PropertyValue<?>>> getPropertyValues();
    public Promise<EnumerablePermission> getPermissions(EnumerablePermission mask);
    public EnumerablePermission getPermissions();

Detail Description
------------------
* public T getNode()
This is the node associated with the Resource

* public Space<?> getSpace()
This is the space for the current resource belongs to

* public Promise<List<PropertyValue<?>>> getPropertyValues()
This returns the property values for current resource

* public Promise<EnumerablePermission> getPermissions(EnumerablePermission mask)
This provides the permission on the resource by providing the permission type

* public EnumerablePermission getPermissions()
This provides all the permission on the resource



