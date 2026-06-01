---
layout: post
title: JSON Parsing
permalink: /json-parsing
---

### JSON Parsing

In web and game development, data persistence relies on converting complex runtime data structures into flat text formats for storage, and then reversing that process later. **JSON parsing** and type conversion are the mechanisms used to translate serialized string sequences back into functional, active data values that code can manipulate. AstroPlatformer reads saved coin totals from localStorage and turns that string into a number the game can use. Parsing JSON-style data or stored values is a key way to make text data useful in gameplay.

Without these transformation routines, saving user progress would be impossible because web-based storage solutions like `localStorage` are strictly limited to retaining plain text strings. If a developer attempts to use stored text directly in mathematical calculations, the program will perform string concatenation instead of numeric addition, turning a score of `5` plus `1` into `51` instead of `6`. Type casting and structured parsing provide a protective boundary, ensuring that external strings match the operational types required by internal engine subsystems.

---

### Managing Persistent State via Serialization and Type Conversion

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. This routine manages the storage lifecycle of collectible tokens by safely reading, modifying, and updating progress keys:

```javascript
/**
 * Synchronizes player progress by retrieving, casting, and updating 
 * the persistent ledger inside the browser's storage container.
 */
function updatePersistentCoinCount() {
  // 1. Retrieve the text string from localStorage. 
  // Use a logical OR string fallback ('0') if the key does not exist yet.
  const rawStorageValue = localStorage.getItem('coinsCollected') || '0';

  // 2. Parse and cast the string value into a base-10 integer.
  // Apply a secondary default fallback (|| 0) if the parsing results in NaN.
  const savedCoins = parseInt(rawStorageValue, 10) || 0;

  // 3. Process the state calculation by adding the collected coin's value
  const newTotal = savedCoins + this.value;

  // 4. Serialize the numeric value back into a string and write it to persistent storage
  localStorage.setItem('coinsCollected', String(newTotal));

  console.log(`[Storage Engine] Local ledger updated. Prior: ${savedCoins} | Appended: ${this.value} | New Total: ${newTotal}`);
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this code reads the saved coin total from localStorage, converts it from text to a number, and stores the updated value again, which makes persistent state usable in gameplay. By using parseInt() along with defensive safety nets, the script actively prevents raw string data from poisoning the arithmetic systems of the platformer. When the engine executes savedCoins + this.value, it can confidently add the values together as pure numbers rather than accidentally matching text chains. O

nce the calculation concludes, the updated score flows directly back into the storage database under the coinsCollected marker, keeping progress intact even if the player closes the window or refreshes the level entirely. Implementing clean parsing boundaries across your input pipelines acts as an excellent shield against data corruption. It ensures that whenever a user returns to your web app, their achievements load smoothly and scale correctly based on their historical game states.
