# Introduction #

> Standalone applications with CouchDB


# Details #

> ## Eclipse users : ##
> > Required libs : lib directory in couchdb-test



> ` In public folder - <Module>.html and <Module>.css (see couchdb-test) `


> ` In <Module>.gwt.xml `
```
    <inherits name='com.os.couchdb.Couchdb'/>
  <define-configuration-property name="couchdb_host" is_multi_valued="false"/>
  <define-configuration-property name="couchdb_port" is_multi_valued="false"/>
  <define-configuration-property name="couchdb_name" is_multi_valued="false"/>
  <define-configuration-property name="couchdb_admin" is_multi_valued="false"/>
  <define-configuration-property name="couchdb_pass" is_multi_valued="false"/>

  <set-configuration-property name="couchdb_host" value="<couchdb host>"/>
  <set-configuration-property name="couchdb_port" value="couchdb_port"/>
  <set-configuration-property name="couchdb_name" value="couchdb_database"/>
  <set-configuration-property name="couchdb_admin" value="admin_user"/>
  <set-configuration-property name="couchdb_pass" value="admin_password"/>

  <add-linker name="couchDBLinker" />

```
> Hosted mode :

Eclipse run configurations / arguments :

` -noserver -startupUrl http://<host>:<port>/<couchdb_name>/_design/<module_name>/<module_name>.html`

**CouchDBLinker and module linker parameters - GWT 2.0**