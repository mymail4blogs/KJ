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

