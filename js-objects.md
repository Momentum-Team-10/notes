# JavaScript Objects

## Objects store information

Think of them like...a lookup table. Or dictionaries. Or card catalogs.

They are made up of **keys** and **values**.

An object can't have two keys with the same name. Each key has to be unique.

---

## How to create a new object

```js
let person = {
  name: 'Amari',
  favoriteColor: 'green',
  job: 'Software developer'
}

console.log(person.name)
// "Amari"
console.log(person.favoriteColor)
// "green"
console.log(person.job)
// "Software developer"
console.log(person.hometown)
// undefined
```

---

## Dot notation vs bracket notation

Both work to retrieve data from objects.
Bracket notation is useful when your key is in a variable or if the key is a string.

```js
let lookupKey = 'job'

console.log(person[lookupKey])
// "Software developer"
```

---

## What can objects hold?

```js
let person = {
  name: 'Amari',
  address: {
    street: '4400 Nightingale Ct.',
    city: 'Sassboro',
    state: 'NC'
  },
  skills: ['Python', 'JavaScript', 'SQL', 'AWS'],
  cool: true,
  birthdate: new Date(1981, 2, 4)
}
```

---

## When do I use arrays and when do I use objects?

- _Arrays_ are for **lists of things**, usually alike
- _Objects_ are for **grouping details about one thing**
- You often combine them:
  - arrays of objects
  - objects with arrays as values

---

## Array of objects

```js
let team = [
  { name: 'Amari', yearsOfExperience: 4 },
  { name: 'Niki', yearsOfExperience: 1 },
  { name: 'Lennon', yearsOfExperience: 2 }
]

let totalYearsOfExperience = 0
for (let member of team) {
  totalYearsOfExperience += member.yearsOfExperience
}
```

---

## Object with arrays

```js
let student = {
  name: 'Ryan',
  testScores: [91, 83, 88, 79, 95]
}

let course = {
  title: 'Advanced Juggling',
  students: [
    {
      name: 'Ryan',
      testScores: [91, 83, 88, 79, 95]
    },
    {
      name: 'Gray',
      testScores: [89, 92, 90, 94, 87]
    }
  ]
}
```

---

## Exercise: Find people by city

Write a function called `findPeopleByCity` that takes two arguments, `city` and `people`. `people` will be an array of objects with the keys `name` and `city`. It should return an array of people who live in the specified city.

```js
let people = [
  { name: 'Autumn', city: 'Durham' },
  { name: 'Parker', city: 'Raleigh' },
  { name: 'Kerry', city: 'Durham' }
]

findPeopleByCity('Durham', people)
// [
//   {name: "Autumn", city: "Durham"},
//   {name: "Kerry", city: "Durham"},
// ]

findPeopleByCity('Raleigh', people)
// [{name: "Parker", city: "Raleigh"}]
```