# MimeTypes
A lightweight C# .net standard library containing a growing list of over 700 mimetypes and 1000 compatible extensions.


### Usage

```csharp

#using Aptacode.MimeTypes;

public void Demo(){
  var mimeType              = MimeTypes.Application.Json;            //Get an extension

  var typeName              = mimeType.Type;            //"application"
  var subTypeName           = mimeType.Subtype;         //"json"
  var toString              = mimeType.ToString;        //"application/json"

  var allMimeTypes          = MimeTypes.All();          //Returns all available MimeTypes
  var filteredMimeTypes     = MimeTypes.All(".jpg");    //Returns all MimeTypes with the given extension

  var allExtensions         = MimeTypes.Extensions.All(); //Returns all available Extensions
  var filteredExtensions    = MimeTypes.Extensions.All(MimeTypes.Application.Json); //Returns all available Extensions for the given MimeType
}

```

### Adding MimeTypes
The main library's sourcecode is generated from a text file containing a list of MimeTypes, users can modify the list, build & run the SourceCodeGenerator project and then overwrite 'MimeTypeGroups.cs' and 'MimeTypeExtensions.cs' using the generated files to add statically typed MimeTypes to the library.
https://github.com/Timmoth/Aptacode.MimeTypes/blob/master/CodeGenerator/mimetypes.txt

Alternatively users can modify add new MimeTypes & modify existing ones at runtime using the static MimeTypes class.
