# Week 1 Day 2 — Code Snippets & Corrections (TypeScript)

This document logs submitted code, corrections, and commentary for Week 1, Day 2 (TypeScript).

---

## Exercise 1: Declare and Print a Variable
**Submitted:**
```ts
let mapScale: number = 50000;
console.log(mapScale);
```
**✅ Correct!** Used proper type annotations and clean `console.log`.

---

## Exercise 2: Classify Cities by Population
**Submitted:**
```ts
type Location = {
    city: string;
    pop: number;
};

const locations: Location[] = [
    { city: "New York", pop: 5000000 },
    { city: "New Haven", pop: 50000 }
];

locations.forEach((loc) => {
    if (loc.pop > 1000000) {
        console.log(`${loc.city} is a Major City.`);
    } else {
        console.log(`${loc.city} is a Small City.`);
    }
});
```
**✅ Correct — clean use of `type`, `forEach`, and conditionals.**

---

## Exercise 3: Loop Through Country Names
**Submitted:**
```ts
const countries: string[] = ["Belgium", "The Netherlands", "Denmark", "Germany", "France"];

countries.forEach((country) => {
    console.log(country);
});
```
**✅ Correct — idiomatic use of `forEach()` and typed arrays.**

---

## Exercise 4: Hemisphere Classification
**Submitted:**
```ts
type City = {
    name: string;
    lat: number;
};

const cities: City[] = [
    { name: "New York", lat: 40 },
    { name: "Sydney", lat: -40 }
];

cities.forEach((loc) => {
    if (loc.lat > 0) {
        console.log(`${loc.name} is in the Northern Hemisphere.`);
    } else {
        console.log(`${loc.name} is in the Southern Hemisphere.`);
    }
});
```
**✅ Clean and effective — well-structured loop and logic.**

---

## Exercise 5: Hemisphere + Size Combo (Challenge)

**Submitted (initial had syntax issues)**
```ts
type City = {
    name: string;
    lat: number;
    pop: number;
    hemi: string;
    size: string;
};

const cities: City[] = [
    { name: "New York", lat: 40, pop: 6000000 },
    { name: "Sydney", lat: -40, pop: 4000000 },
    { name: "Key West", lat: 20, pop: 200000 },
];

cities.forEach((loc) => {
    if (loc.lat > 0) {
        let loc.hemi: "Northern"};
    } else {
        let loc.hemi: "Southern"};
    if (loc.pop > 5000000) {
        let loc.size: "Mega"};
    if (1000000 >= loc.pop >= 5000000) {
        let loc.size: "Major"};
    } else {
        let loc.size: "Small"};
    console.log(`${loc.name} is a {loc.size} City in the {loc.hemi} Hemisphere.`)
});
```
**✅ Final Working Version:**
```ts
type City = {
    name: string;
    lat: number;
    pop: number;
    hemi: string;
    size: string;
};

const cities: City[] = [
    { name: "New York", lat: 40, pop: 6000000, hemi: "", size: "" },
    { name: "Sydney", lat: -40, pop: 4000000, hemi: "", size: "" },
    { name: "Key West", lat: 20, pop: 200000, hemi: "", size: "" }
];

cities.forEach((loc) => {
    if (loc.lat > 0) {
        loc.hemi = "Northern";
    } else {
        loc.hemi = "Southern";
    }

    if (loc.pop > 5000000) {
        loc.size = "Mega";
    } else if (loc.pop >= 1000000 && loc.pop <= 5000000) {
        loc.size = "Major";
    } else {
        loc.size = "Small";
    }

    console.log(`${loc.name} is a ${loc.size} City in the ${loc.hemi} Hemisphere.`);
});
```

**Fixes Made:**
- Assigned properties to existing object keys instead of using `let`
- Used correct conditional logic (`else if`)
- Fixed string interpolation syntax

            Original Response:
    	1.	You don’t need to declare hemi and size inside the loop with let — those fields already exist on the object from your City type.
    	•	Just assign them like: loc.hemi = "Northern";
    	2.	The comparison 1000000 >= loc.pop >= 5000000 doesn’t work in TypeScript/JavaScript — use a chained comparison with &&.
    	3.	Your console.log had a small issue: it used {loc.size} instead of ${loc.size} (missing the $).
    	4.	Semicolons and closing braces were a little off — we’ll clean those up.


---
