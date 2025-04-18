# Week 1 Day 4 — Code Snippets & Corrections (Rust)

This document logs submitted Rust code, corrections, and commentary for Week 1, Day 4.

---

## Exercise 1: Declare and Print a Variable
**Submitted:**
```rust
let mut map_scale = 50_000;
println!("{}", map_scale);
```
**✅ Correct — Clean formatting and use of numeric underscores.**

---

## Exercise 2: Population Classification
**Submitted:**
```rust
let population = 8_000_000;

if population >= 1_000_000 {
    println!("Major City");
} else {
    println!("Small City");
}
```
**✅ Correct — Strong conditional logic and readable structure.**

---

## Exercise 3: Loop Through Country Names
**Submitted:**
```rust
let countries = vec![
    "Belgium".to_string(),
    "The Netherlands".to_string(),
    "Denmark".to_string(),
    "Germany".to_string(),
    "France".to_string(),
];

for country in countries {
    println!("{}", country);
}
```
**✅ Correct — Great use of `vec![]`, `String`, and `for` loop.**

---

## Exercise 4: Hemisphere Classification by Latitude
**Submitted:**
```rust
struct City {{
    name: String,
    lat: f64,
}}

let cities = vec![
    City {{ name: "New York".to_string(), lat: 40.0 }},
    City {{ name: "Sydney".to_string(), lat: -40.0 }},
    City {{ name: "Key West".to_string(), lat: 30.0 }},
];

for city in cities {{
    if city.lat > 0.0 {{
        println!("{} is in the Northern Hemisphere.", city.name);
    }} else {{
        println!("{} is in the Southern Hemisphere.", city.name);
    }}
}}
```
**✅ Correct — Excellent use of struct, float comparison, and iteration.**

---

## Exercise 5: City Size + Hemisphere Classification (Challenge)

**Initial Attempt:**
- Tried to store and mutate `size` and `hemi` fields inside the loop
- Encountered Rust's restrictions around field reassignment and ownership

**Final Working Version:**
```rust
struct City {{
    name: String,
    lat: f64,
    pop: u32,
}}

let cities = vec![
    City {{ name: "New York".to_string(), lat: 40.0, pop: 6_000_000 }},
    City {{ name: "Sydney".to_string(), lat: -40.0, pop: 3_000_000 }},
    City {{ name: "Key West".to_string(), lat: 30.0, pop: 400_000 }},
];

for city in cities {{
    let size = match city.pop {{
        n if n > 5_000_000 => "Mega",
        1_000_000..=5_000_000 => "Major",
        _ => "Small",
    }};

    let hemi = if city.lat > 0.0 {{
        "Northern"
    }} else if city.lat < 0.0 {{
        "Southern"
    }} else {{
        "Equator"
    }};

    println!("{} is a {} City in the {} Hemisphere.", city.name, size, hemi);
}}
```

**✅ Final version is clean, idiomatic, and matches real-world Rust best practices.**