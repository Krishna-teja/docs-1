---
slug: formats
---
ServiceStack supports 6 response formats out of the box:

- [JSON](https://github.com/ServiceStack/ServiceStack.Text)
- XML
- [SOAP 1.1/1.2](?id=SOAP-support)
- [JSV](https://github.com/ServiceStack/ServiceStack.Text#servicestacktypeserializer-and-the-jsv-format) _(hybrid CSV-style escaping + JSON format that is optimized for both size and speed)_
- [CSV](?id=csv-format)
- [HTML5 Report](?id=HTML5ReportFormat) _(provides a readable and semantic HTML layout letting you visualize all the data returned by your web service)_
- [HTML with Markdown Razor](?id=Markdown-Razor) _(Razor combined with markdown)_

### Additional Formats

Additional Formats are available as [external Plugins](?id=Plugins):

- [HTML with MVC Razor](http://razor.servicestack.net/)
- [Message Pack](?id=MessagePack-Format)
- [Protocol Buffers](?id=Protobuf-format)

## Rest endpoint

You can define which format should be used by adding a `.{format}` extension:

 - `.json`
 - `.xml`
 - `.jsv`
 - `.csv`
 - `.html`

Or by appending `?format={format}` to the end of the URL:

- `?format=json`
- `?format=xml`
- `?format=jsv`
- `?format=csv`
- `?format=html`

> Example: http://mono.servicestack.net/hello/World!?format=json

Alternatively ServiceStack also recognizes which format should be used with the `Accept` [http header](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields):

- `Accept: application/json`
- `Accept: application/xml`

As you can see, this approach only works with `json` and `xml`.

## Default endpoint

    /[xml|json|html|jsv|csv]/[reply|oneway]/[servicename]

Examples:

 - /json/reply/Hello (will be JSON)
 - /xml/oneway/SendEmail (will be XML)

## SOAP endpoint

The SOAP endpoint only supports XML of course.

> Tip: If you have forgotten the details about the specific endpoints, you can re-read [this article](?id=Endpoints)

