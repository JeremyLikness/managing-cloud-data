# Managing Data in the Cloud

This is the demo walkthrough and resource for the presentation, "Managing Data in the Cloud."

## Pre-requisites

* An Azure subscription. Don't have one? [Get one for free](https://jlik.me/fsj)
* [Azure Storage Emulator](https://jlik.me/fsk)
* [Azure Storage Explorer](https://jlik.me/fsn)
* [Visual Studio](https://jlik.me/fso)

## Create a Storage Account

👩‍🎓👨‍🎓 [Learn how to create a storage account](https://jlik.me/ftn)

1. Create a new Storage Account
2. Place it in a new resource group
3. Use defaults for V2 and RA-GRS and "Hot"
4. Create

### Review the Features

1. Navigate to "Blobs"
2. Navigate to "Tables"
3. Navigate to "Files"
4. Click "➕ File share"
5. Show options

## Blob Storage Demo

👩‍🎓👨‍🎓 [Learn about blob storage](https://jlik.me/fto)

Start with the account created in the previous step.

1. Create a container named "images"
2. Set access level to "Blob"
3. Show the container properties
4. Navigate to "Access policy"
5. Show "Add policy" under "Stored access policies"
6. [Explain SAS](https://jlik.me/ftp) at a high level
7. Show "Add policy" and explain "[Immutable blob storage](https://jlik.me/ftq)"
8. Drill into the container
9. Begin process to upload `assets\AzureStorageBlob`
10. Open "Advanced"
11. Type `icons` in "Uploaded to folder"
12. Navigate into `icons`
13. Show the blob properties
14. Explain "[acquire lease](https://jlik.me/ftr)"
15. Acquire and break the lease
16. Copy the URL
17. Open in an "in private" or "incognito" window
18. Go to access policies (Blob level)
19. Show [role assignment example](https://jlik.me/fts)

## Write to Blob Storage

This demo is based on the Microsoft Ignite | The Tour demo for the [DEV50 - Serverless Module](https://github.com/Microsoft/IgniteTheTour/tree/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV50).

1. Start with an initialized database
2. Open Storage Explorer and show the existing SKUs
3. Use the CLI to add a sample SKU:
    `dotnet run add 2085`
1. Run the command to add the image:
    `dotnet run set-image 2085 2085.jpg`
1. Show the updated image in Storage Explorer
2. Navigate to show the image
3. Review the related code
    1. [Access the image and pass the stream](https://github.com/Microsoft/IgniteTheTour/blob/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV50/src/TailwindTraderServerless/CLI/Image.cs)
    1. [Create container](https://github.com/Microsoft/IgniteTheTour/blob/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV50/src/TailwindTraderServerless/DataAccess/StorageAccess.cs#L41-L52)
    1. [Upload the image](https://github.com/Microsoft/IgniteTheTour/blob/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV50/src/TailwindTraderServerless/DataAccess/StorageAccess.cs#L94-L108)

## NoSQL Demo

The NoSQL demo is split into two parts.

### Flights database

The instructions to set up the flights database are in [this GitHub repo](https://github.com/anthonychu/cosmosdb-gremlin-flights).

📄 Learn about [Gremlin in Azure Cosmos DB](https://jlik.me/ftt)

1. Show the [running demo](https://cosmosdb-flights.azurewebsites.net/). SEA-YVR has few routes, SEA-ATL has many.
2. Show steps to create an Azure Cosmos DB instance in the portal
3. Show the graph in data explorer (web)
4. Use 'LED' as a `g.V('LED')` query to grab a vertex
5. Use `g.V('LED').in()` to show incoming flights
6. Show the backing JSON (just documents!)
7. [Walk through the code](https://github.com/anthonychu/cosmosdb-gremlin-flights/blob/master/CosmosDBGremlinFlights.Web/Controllers/HomeController.cs)

### Link Shortener

Read the [related article](https://jlik.me/ftu) and [browse the repository](https://github.com/JeremyLikness/jlik.me).

1. Shorten a link
2. Show the associated table storage
1. [Code to insert the link](https://github.com/JeremyLikness/jlik.me/blob/master/jlikme.corefn/FunctionHost.cs#L98-L212)
2. [Code for the redirect](https://github.com/JeremyLikness/jlik.me/blob/master/jlikme.corefn/FunctionHost.cs#L214-L277)
3. [Code to insert metadata](https://github.com/JeremyLikness/jlik.me/blob/master/jlikme.corefn/FunctionHost.cs#L285-L384)
4. Execute the redirect
5. Navigate to document database
6. Query initial documents and show format
7. Sort by `_ts` descending and show newer documents
8. Open the Power BI dashboard and show data "deep dive"
9. Drill into the related Application Insights
10. Show the performance tab and drill between functions and dependencies

## Azure SQL

The demo for SQL is based on the [DEV10: Designing Resilient Cloud Applications](https://github.com/Microsoft/IgniteTheTour/tree/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV10) repository.

👩‍🎓👨‍🎓 [Learn how to provision an Azure SQL Server](https://jlik.me/ftv)

1. Show the Azure SQL account and the available features
2. Drill into SQL databases then `tailwind`
3. Show geo-replication
4. Show query editor
5. Execute `select top 5 * from dbo.Inventory`
6. Show [InventoryManager](https://github.com/Microsoft/IgniteTheTour/blob/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV10/src/inventory-service/InventoryService.Api/Services/InventoryManager.cs)
7. Show [SqlInventoryData](https://github.com/Microsoft/IgniteTheTour/blob/master/DEV%20-%20Building%20your%20Applications%20for%20the%20Cloud/DEV10/src/inventory-service/InventoryService.Api/Services/SqlInventoryData.cs)

## Database Migration Services

Show the [database migration services](https://jlik.me/fs2) page and various options.

Follow [@JeremyLikness](https://twitter.com/JeremyLikness) on Twitter.
