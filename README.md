# PersonAPI

A small .NET 8 REST API for working with persons and their favorite colors.

## What it does
The app reads person data from a CSV file (`sample-input.csv`) and gives you endpoints to list/lookup people.  
Each person has: ID (line number in the CSV), first/last name, address, and a favorite color.

### Color Mapping
- 1 = blau (blue)  
- 2 = grün (green)  
- 3 = violett (purple)  
- 4 = rot (red)  
- 5 = gelb (yellow)  
- 6 = türkis (turquoise)  
- 7 = weiß (white)  

## Running it

dotnet run

The API will then be available at:  
- http://localhost:5000  
- https://localhost:5001  

## Endpoints

### GET /persons
Lists all persons.  

    curl http://localhost:5000/persons

---

### GET /persons/{id}
Get a person by ID (1 = first line in the CSV).  

    curl http://localhost:5000/persons/1

If the ID doesn’t exist, you get a `404 Not Found`.  

---

### GET /persons/color/{color}
Get all persons with the given favorite color (case-insensitive).  

    curl http://localhost:5000/persons/color/rot  
    curl http://localhost:5000/persons/color/ROT

If no match: returns an empty array `[]`.  

---

## Tests
Integration tests with xUnit + WebApplicationFactory. Run them with:  

    dotnet test

