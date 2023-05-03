# Setup

HTTPgrid offers a REST API to interact with the service, and easy to use libraries to interact with the API.

HTTPgrid also has an API reference and OpenAPI (formerly Swagger) specifications at the API documentation page which you can always refer to the exact schemas and endpoints available in our API.

When working with HTTPgrid you can either use our REST API directly, or using any of our libraries. In this document we'll cover how to install them for each platform.

## JavaScript/TypeScript

Install the library

```bash
npm install httpgrid
// Or
yarn add httpgrid
```

Then you can just use them as follows

```typescript
import { HTTPgrid } from "httpgrid";

const httpGrid = new HTTPgrid("AUTH_TOKEN");

const message = await httpGrid.message.create(application.id, {
    channels: [],
    eventType: 'user.created',
    payload: {
        email: 'foo.bar@example.com',
    },
    uid = '3a1e7928-8498-41b5-beaa-7f6d89ed0133'
});
```

## C#

Install the library

```bash
dotnet add package HTTPgrid.net
# or
NuGet\Install-Package HTTPgrid.net
```

```csharp
using HTTPgrid.net;
using HTTPgrid.net.Domain.Entities;

var httpGridClient = new HTTPgridClient("AUTH_TOKEN");

var message = await httpGridClient.Message.Create("my-application", new Message()
{
    Channels = new string[0],
    EventType = "user.created",
    Payload = new 
    {
        Email = "foo.bar@example.com"
    },
    Uid = Guid.NewGuid().ToString(),
});
```

<p align="right"><a href="/introduction/QUICKSTART.md">Go to Quickstart</a></p>
