Node
=======
Node is the actual functioning interface.

Methods
---------------
Following  functionality provided by Node::

    public Long getId();
    public Promise<? extends WritableNode> writable();
    public Promise<? extends ReadableNode> readable();
    public void writeWith(DataWriter writer);
    /**
    * Convenience method to write this object to JSON (using writeWith and a registered JSON writer)
    * @return the JSON content of the object
    */
    public String getJSON();

