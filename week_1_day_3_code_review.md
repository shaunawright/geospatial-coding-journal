# Week 1 Day 3 — Code Snippets & Corrections (SQL)

This document logs submitted SQL code, corrections, and commentary for Week 1, Day 3.

---

## Exercise 1: Select Names and Populations
**Submitted:**
```sql
SELECT name, population FROM cities;
```
**✅ Correct — Clean SELECT query.**

---

## Exercise 2: Classify Cities by Population Size
**Submitted:**
```sql
SELECT
    name,
    population,
    CASE
        WHEN population > 5000000 THEN 'Mega City'
        WHEN population >= 1000000 THEN 'Major City'
        ELSE 'Small City'
    END AS city_size
FROM cities;
```
**✅ Correct — Good structure and readable logic.**

---

## Exercise 3: Hemisphere Classification by Latitude
**Submitted:**
```sql
SELECT
    name,
    lat,
    CASE
        WHEN lat > 0 THEN 'Northern'
        ELSE 'Southern'
    END AS hemi
FROM cities;
```
**✅ Correct — Clear and concise.**

---

## Exercise 4: Filter to Southern Hemisphere
**Submitted:**
```sql
SELECT name FROM cities WHERE lat < 0;
```
**✅ Correct — Applied WHERE clause properly.**

---

## Exercise 5: Combined Classification + Filtering

**Initial Attempt (Issue):**
```sql
-- Tried to use 'size' alias in WHERE clause, which isn't allowed.
```

**Corrected Version (Using Subquery):**
```sql
SELECT *
FROM (
    SELECT
        name,
        pop,
        lat,
        CASE
            WHEN pop > 5000000 THEN 'Mega City'
            WHEN pop >= 1000000 THEN 'Major City'
            ELSE 'Small City'
        END AS size,
        CASE
            WHEN lat > 0 THEN 'Northern'
            WHEN lat < 0 THEN 'Southern'
            ELSE 'Equator'
        END AS hemi
    FROM cities
) AS classified
WHERE size IN ('Mega City', 'Major City');
```

**✅ Final version works as intended — clean use of subquery and conditional logic.**

---

## Extra:
**Visual diagram created** to explain why aliases like `size` can’t be used in `WHERE` clauses without subqueries. This reinforces understanding of SQL processing order.

---