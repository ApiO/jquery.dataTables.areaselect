# jquery.dataTables.areaselect

[![NuGet](https://img.shields.io/nuget/v/jquery.dataTables.areaselect.svg)](https://www.nuget.org/packages/jquery.dataTables.areaselect) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://opensource.org/licenses/MIT)

Extension of **[jquery.dataTables](https://www.datatables.net/)** plugin for area selection.

![](http://acuisinier.com/images/jquery.dataTables.multiselect.png)

## Documentation & demo

> For code sample check out the *index.html* file or go to [live demo](http://acuisinier.com/demo/jquery.dataTables.areaselect).
  
**Minimal browser compatibility**

Web browser|Version 
---|---
Chrome|Ok
Firefox|v3.5
IE|v9
Opera|v10
Safari|v4

**Dependencies**

> **jQuery v1.11.3** at least. Works perfectly on higher versions.  
> **jquery.dataTables v1.10.8** or higher version.
> **[jquery.dataTables.select extension](https://github.com/DataTables/Select)**


**Features**

- Drag & drop onto table row to select a range of rows.
- Hold Ctrl to add item to an existing selection.
  
**Usages**

```html
	<!-- reference both css and js files -->
    <script src="js/jquery.dataTables.areaselect.js"></script>
    
	<!-- Add a table to your page -->
	<table id="myTable"></table>
 ```
 
```javascript
	// initializes dataTable as usual
	$("#myTable").dataTable({
		data: ...,
		columns: [ ... ],
		select: true, // Activates Select extension
		initComplete: function () {
			// enables area selection extension
			$("#myTable").AreaSelect();
		}
	});
```
 
```javascript
	// Select events callback
	$("#myTable").DataTable()
		.on("select", function (e, dt, type, indexes) {
			if (type === "row") {
		        	var data = $("#myTable").DataTable().rows(indexes).data()[0];
		        	console.info("select", data);
		    	}
		})
		.on("deselect", function (e, dt, type, indexes) {
			if (type === "row") {
				var data = $("#myTable").DataTable().rows(indexes).data();
				console.info("deselect", data);
			}
		});
```

##License

MIT License

Copyright (c) 2014-2016 ApiO

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
