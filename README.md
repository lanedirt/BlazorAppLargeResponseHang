# Bug reproduction instructions

This repository is used to reproduce a bug where if a page contains a large amount of HTML elements the request hangs in .NET 8 Preview 6 Blazor and won't return a result.

**Tested with:**

`dotnet --version`: 8.0.100-preview.6.23330.14
`Visual Studio`: Version 17.7.0 Preview 3.0

## To reproduce bug:
1. Clone this repository
2. Run the BlazorApp1 project
3. When the browser opens, the index page ("/") hangs and won't load.

## Comments
The `BlazorApp1\Pages\Index.razor` file contains a few duplicated `<table>` elements. 

If you delete one of these elements, the page will start to work. Therefore my conclusion is that this bug is caused by the amount of data, not necessarily any of the elements themselves.