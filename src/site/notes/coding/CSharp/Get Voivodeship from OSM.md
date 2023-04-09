---
{"title":"Get Voivodeship from OSM","dg-publish":true,"tags":["coding/CSharp"],"language":"en","permalink":"/coding/c-sharp/get-voivodeship-from-osm/","dgPassFrontmatter":true}
---

up:: [[coding/CSharp/CSharp\|CSharp]]

```csharp
using NetTopologySuite.Features;  
using NetTopologySuite.IO;  
using RestSharp;  
using System.Text.Json;
internal static async Task<string?> GetStateFromNominatim(  
double lat,  
double lon)  
{  
var client = new RestClient("https://nominatim.openstreetmap.org");  
var request = new RestRequest("reverse");  
request.AddParameter("format", "json");  
request.AddParameter("lat", lat);  
request.AddParameter("lon", lon);  
request.AddParameter("zoom", 10);  
request.AddParameter("addressdetails", 1);  
await Task.Delay(1000);  
var response = await client.ExecuteAsync(request);  
if (response.IsSuccessful)  
{  
if (response.Content != null)  
{  
var jsonResponse = JsonDocument.Parse(response.Content);  
var address = jsonResponse.RootElement.GetProperty("address");  
var state = address.GetProperty("state").GetString();  
return state;  
}  
}  
else  
{  
Console.WriteLine($"Reverse geocoding error: {response.StatusCode}");  
return null;  
}  
return string.Empty;  
}
```

## Get Train stations from geojson

```csharp
internal static List<Station> SeedStations()  
{  
var options = new JsonSerializerOptions { PropertyNameCaseInsensitive = true };  
// get root path of repository  
var rootPath = Path.GetFullPath(Path.Combine(AppContext.BaseDirectory, "..\\..\\..\\..\\..\\"));  
// get path to stations.json Slp\src  
var stationsPath = Path.Combine(rootPath, "stations.geojson");  
// read stations.json  
var geoJson = File.ReadAllText(stationsPath);  
var featureCollection = new GeoJsonReader().Read<FeatureCollection>(geoJson);  
var stations = new List<Station>();  
foreach (var feature in featureCollection)  
{  
var properties = feature.Attributes;  
var coordinates = feature.Geometry.Coordinate;  
var station = new Station  
{  
Name = (string)properties["name"],  
Latitude = coordinates.Y,  
Longitude = coordinates.X  
};  
stations.Add(station);  
}  
return stations;  
}
```
