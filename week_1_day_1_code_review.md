# Week 1 Day 1 — Code Snippets & Corrections

This document contains all the code snippets submitted by the student for the exercises, along with corrected versions and explanation notes.

---

## Exercise 1: Define and Print a Variable
**Submitted:**
```python
map_scale = 50000
print(map_scale)
```

**✅ Correct — No corrections needed.**

---

## Exercise 2: Classify City by Population
**Submitted (initial):**
```python
if population > 1000000:
print(“Major City”)
else:
print(“Small City”)
```

**Correction:**
```python
population = 1200000

if population > 1000000:
    print("Major City")
else:
    print("Small City")
```

**Fixes Made:**
- Defined `population` before using it
- Fixed indentation (4 spaces)
- Replaced curly quotes with straight quotes

---

## Exercise 3: Loop Through a List of Countries
**Submitted:**
```python
countries = ["Belgium", "The Netherlands", "Denmark", "Germany", "France"]

for country in countries:
    print(country)
```

**✅ Correct — Well done!**

---

## Exercise 4: Hemisphere Based on Latitude
**Submitted:**
```python
locations = [
    {"city": "Quito", "lat": -0.1807, "lon": -78.4678},
    {"city": "Oslo", "lat": 59.9139, "lon": 10.7522}
]

for loc in locations:
    if loc["lat"] > 0:
        print(f"{loc['city']} is in the Northern Hemisphere")
    else:
    print(f"{loc['city']} is in the Southern Hemisphere")
```

**Correction:**
```python
for loc in locations:
    if loc["lat"] > 0:
        print(f"{loc['city']} is in the Northern Hemisphere")
    else:
        print(f"{loc['city']} is in the Southern Hemisphere")
```

**Fixes Made:**
- Fixed indentation under the `else:` block

---

## Exercise 5: Classify Cities by Population Size
**Submitted:**
```python
cities = [
    {"name": "Tokyo", "population": 6000000},
    {"name": "Osaka", "population": 3000000},
    {"name": "Kyoto", "population": 2000000},
    {"name": "Nara", "population": 500000},
    {"name": "Chiba", "population": 600000}
]

for city in cities:
    if city["population"] > 5000000:
        print(f"{city['name']} is a Mega City")
    elif city["population"] > 1000000 and city["population"] < 5000000:
        print(f"{city['name']} is a Major City")
    else:
        print(f"{city['name']} is a Small City")
```

**✅ Correct — Nice work!**
- Optional improvement: Use chained comparison for readability:
```python
elif 1000000 <= city["population"] <= 5000000:
```

---

## Go Further Challenge: Hemisphere + Size Classification

**Submitted (initial attempt):**
```python
cities = [
    {"name": "New York", "pop": 6000000, "lat": 40},
    {"name": "Boston", "pop": 3000000, "lat": 38},
    {"name": "Philadelphia", "pop": 900000, "lat": 36}
]

for city in cities:
    if city["lat"] > 0:
        hemi = "Northern"
    else:
        hemi = "Southern"

for city in cities:
    if city["pop"] > 5000000:
        size = "Mega City"
    elif 1000000 <= city["pop"] <= 5000000:
        size = "Major City"
    else:
        size = "Small City"

for city in cities:
    print(f"{city['name']} is a {city['size']} in the {city['hemi']} Hemisphere.")
```

**Correction:**
```python
cities = [
    {"name": "New York", "pop": 6000000, "lat": 40},
    {"name": "Boston", "pop": 3000000, "lat": 38},
    {"name": "Philadelphia", "pop": 900000, "lat": 36}
]

for city in cities:
    if city["lat"] > 0:
        city["hemi"] = "Northern"
    else:
        city["hemi"] = "Southern"

    if city["pop"] > 5000000:
        city["size"] = "Mega City"
    elif 1000000 <= city["pop"] <= 5000000:
        city["size"] = "Major City"
    else:
        city["size"] = "Small City"

for city in cities:
    print(f"{city['name']} is a {city['size']} in the {city['hemi']} Hemisphere.")
```

**Fixes Made:**
- Combined logic into a single loop
- Stored `"size"` and `"hemi"` directly in the dictionary so they persist

---