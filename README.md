# Epos.LaTeX.WebApi

![Build Status](https://eposgmbh.visualstudio.com/_apis/public/build/definitions/f8efcc28-0cef-4500-a9e4-7b6d4c7f3c3d/6/badge)

(Build and deployment to [Dockerhub](https://hub.docker.com/) is automated with
[Visual Studio Team Services](https://www.visualstudio.com/team-services).)

ASP.NET Core Web API to convert LaTeX to a PNG Image

POST raw JSON (application/json) body to `http://[host]:81/api/latex`.

```javascript
{
    laTeX: "a^2 + b^2 = c^2",
    textColor: "777777" // HTML "#"-Format
}
```

You get back:

```
{
    "isSuccessful": true,
    "errorMessage": null,
    "pngImageData": "iVBORw0KGgoAAAANSUhEUgAABZ..."
}
```

`pngImageData` is a Base64-encoded PMG-Image. [Json.NET](https://www.newtonsoft.com/json) deserializes this into a `byte[]` array.
