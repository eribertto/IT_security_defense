LDAP, or Lightweight Directory Access Protocol, is an open industry-standard
protocol for accessing and maintaining directory services. When we say directory
services, we're referring to something similar to a phone or email directory.
It's most commonly used as a backend for authentication of accounts. The LDAP
specification describes the data structure of the directory itself. And defines
functions for interacting with the service, like performing look ups and
modifying data. You can think of a directory like a database, but with more
details or attributes, describing entities within the database. The structure of
an LDAP directory is a sort of tree layout and is optimized for retrieval of
data more so than writing. Think of it as being similar to a phone book being
used for looking up data far more often than making modifications to that data.
Directories can be hosted across lots of different LDAP servers to facilitate
more rapid look ups, and are kept in sync through replication of the directory.
So what kind of data gets stored in directory entry, exactly? Similar to an
address book, an entry for a particular user will contain information pertaining
to that user account, like their first and last name, phone number, desk
location, email address, login shell, and other such data. Along with object
attributes the location of an entry within the overall data structure will
represent information pertaining to the objects as relationships between
objects. Because LDAP uses a tree structure called a Data Information Tree,
objects will have one parent and can have one or more children that belong to
the parent object. You can also think about this like a file system with a root
file system in folders under that. The folder an object belongs to will provide
information about that object because of its relationship to the parent object.
In LDAP language, we call these folders Organizational Units, or OUs. They let
us group related objects into units like people or groups to distinguish between
individual user accounts and groups that accounts can belong to. This tree
structure also allows for inheritance and nesting of objects, where attributes
or properties of a parent object can be inherited by children further down the
tree. Now, since it is possible for entries in the directory to share
attributes, there must be a unique identifier for each entry. We call this,
Distinguished Name, or DN. Coming back to our file system analogy, you can think
of a DN as a full path to a file as opposed to a file name. This is because you
can have multiple files with the same file name across a file system. But the
fully qualified path to the file would describe one unique file. Some of the
more common operations that can be called by a client to interact with an LDAP
server are bind, which is how clients authenticate to the server. StartTLS,
which permits a client to communicate using LDAP v3 over TLS. Search, for
performing look ups and retrieval of records. Add/delete/modify which are
various operations to write data to the directory, and Unbind, which closes the
connection to the LDAP server. Now, there are many implementations of LDAP
servers, like Active Directory from Microsoft and OpenLDAP for open source
implementations.