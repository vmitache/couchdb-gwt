# Introduction #

Generate map/reduce,update,filter,lucene search,show,list,view javascript functions using GWT compiler/linker


# Details #
> Eclipse:


> Use module `FnModule.gwt.xml` - right now this name is not configurable - just fill in the couchdb appropriate parameters

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE module PUBLIC "-//Google Inc.//DTD Google Web Toolkit 1.7.1//EN" "http://google-web-toolkit.googlecode.com/svn/tags/1.7.1/distro-source/core/src/gwt-module.dtd">
<module>
  <inherits name="com.os.couchdbjs.Couchdb_js" />
  <entry-point class='com.os.client.FnModule'/>
  <source path="client"/>
  <set-configuration-property name="couchdb_host" value="host"/>
  <set-configuration-property name="couchdb_port" value="port"/>
  <set-configuration-property name="couchdb_name" value="dbName"/>
  <set-configuration-property name="couchdb_admin" value="adminUser"/>
  <set-configuration-property name="couchdb_pass" value="adminPasswd"/>
</module>
```

Create java classes for the javascript functions to be generated - example :
```
@FilterFn(designDocName="dtest",filterName="designDocs")
public class FilterTest extends AbstractFilter {

	@Override
	public boolean filter(BaseDocument pDoc, BaseRequest pRequest) {
		return pDoc.getId().startsWith("_design/");
	}
}

```

Enable annotation processing in Eclipse. Set generated source directory to "generated" - may be different. Set factory path to `<dir_name>/couchdb_js.jar`
> Use the annotations per javascript function type to be generated.
The annotation processor will generate one GWT module for each function to be generated.
Use GWT plugin to compile the generated modules (output style  set to 'Obfuscated') - they will translate java code to javascript and upload them to couchdb design docs. Check couchdb-js-test for examples.
More examples to follow..



