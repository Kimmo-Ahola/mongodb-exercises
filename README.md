# Uppkopping till databas

Ni kan med ett extension i VSCode koppla upp er till en databas (Read access endast) och göra övningarna. För att koppla upp er mot databasen klistrat ni in den länk som finns i lektionsmaterialet.

Om ni har Compass installerat kan ni köra detta lokalt genom att ladda in det dataset som finns uppladdat i en egen collection.



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

# 🟢 BASIC QUESTIONS

---

### 1️⃣ Find the movie missing length and update it

---

### 2️⃣ Find actors missing last name

---

### 3️⃣ Count Action movies + list them

---

### 4️⃣ Movies with rating > 8.1

---

### 5️⃣ Fix gross_worldwide not starting with "$"
