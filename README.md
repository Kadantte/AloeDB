![Logo](https://raw.githubusercontent.com/Kirlovon/AloeDB/master/other/head.png)

<h3 align="center">AloeDB</h3>
<p align="center">Light, Embeddable, NoSQL database for Deno</p>

<p align="center">
    <b>Work in progress!</b>
</p>

## Features
* ✨ Simple to use API, similar to [MongoDB](https://www.mongodb.com/)!
* ⚖ No dependencies, ___even without [std](https://deno.land/std)!___
* 🚀 Optimized for a large number of operations.
* 📁 Stores data in JSON file.

## Example
```typescript
import { Database } from 'https://deno.land/x/aloedb/mod.ts'

// Structure of stored documents
interface Film {
    title: string;
    year: number;
    film: boolean;
    genres: string[];
    authors: { director: string };
}

// Initialization
const db = new Database<Film>('./path/to/the/file.json');

// Insert operations
await db.insertOne({ 
    title: 'Drive', 
    year: 2011,
    film: true,
    genres: ['crime', 'drama', 'noir'],
    authors: { director: 'Nicolas Winding Refn' }
});

// Search operations
const found = await db.findOne({ title: 'Drive', film: true });

// Delete operations
await db.deleteOne({ title: 'Drive' });
```
_P.S: More example can be found [here]()!_