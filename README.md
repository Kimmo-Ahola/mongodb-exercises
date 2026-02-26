# Klona detta repo till er själva

Skapa ett eget repository på er GitHub

Inuti VSCodes terminal:
git clone https://github.com/Kimmo-Ahola/mongodb-exercises.git
eller klicka på clone-knappen inuti VSCode och klistra in länken där.

I terminalen i VSCode skriver ni sedan:
`git remote remove origin`
`git remote add origin yourlinkhere`

Detta tar bort kopplingen till mitt repo och ni lägger sedan till en koppling till ert eget repo.


# Uppkopping till databas

Ni kan med ett extension i VSCode koppla upp er till en databas (Read access endast) och göra övningarna. För att koppla upp er mot databasen klistrat ni in den länk som finns i lektionsmaterialet.

Om ni har Compass installerat kan ni köra detta lokalt genom att ladda in det dataset som finns uppladdat i en egen collection.

<img width="443" height="143" alt="image" src="https://github.com/user-attachments/assets/0671685f-827b-42ed-8166-d993fa93c67f" />
<img width="691" height="501" alt="image" src="https://github.com/user-attachments/assets/051eabec-83ef-461d-ab5b-064a0067c599" />



# Förenklat schema för översikt

Kom ihåg att MongoDB är en dokumentdatabas och i dessa databaser är denormalisering OK och uppmuntras.

MongoDB är schema-less vilket betyder att det är utan databasschema eller har ett flexiblare ("färre regler") schema än SQL har.

Översikt över schemat för denna uppgift:

{} 
= ett objekt. 
  Ett objekt innehåller key-value-par precis som i JSON, 
  men i vår dokumentstruktur skriver vi normalt inte "" runt key:n.

String | null 
= fältet kan innehålla en sträng eller vara null. 
  Symbolen "|" betyder "eller", alltså en unionstyp.

[String] 
= en lista/array av strängar. 
  Exempel: ["Kimmo", "Lars"]

cast = [{}] 
= en lista/array av objekt. 
  Varje objekt representerar en skådespelare och kan t.ex. ha fälten:
    actor: String
    role: String | null

```json
{
  _id: ObjectId,

  // Basic info
  name: String,
  year: String,
  length: String | null,
  storyline: String,
  url: String,

  // Ratings
  score: String,
  top_rate: String,
  popularity: String | null,

  // Financial
  budget: String | null,
  gross_worldwide: String | null,

  // Awards
  wins: String,
  nominations: String | null,

  // Origin
  origin_language: String | null,
  origin_countries: [String],

  // Categories
  genres: [String],
  production_companies: [String],

  // People
  directors: [String],
  writers: [String],

  cast: [
    {
      actor: String,
      role: String | null
    }
  ]
}
```


---

För övningarna rekommenderas det att ni gör en övning i taget och pushar upp ändringen till GitHub via Source Control.

# TODO, skriv bättre övningar
