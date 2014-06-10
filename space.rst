Space
========

Space documentation

Methods
---------------
Following  functionality provided by Space::

    public T getNode();

    public <R extends Node> Promise<Resource<R>> createOrUpdateResource(R resource);

    public Promise<Boolean> allows(Resource<?> resource);

    public Promise<Boolean> allows(Space<?> space);

    public Promise<List<PropertyType>> getAvailableProperties(Resource<?> resource);

    /**
     * Get the resource template instance with the given class and key for this space
     * @param key
     * @param type
     * @return
     */
    public <T extends ResourceTemplate> Promise<T> getTemplate(String key, Class<T> type);