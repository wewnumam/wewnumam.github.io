---
title: "The Power of Variable Names"
date: 2022-12-16T09:22:51+07:00
draft: false
tags: ["Programming", "Technical Skill"]
---

## Meaningful Variable Names
> Choosing good names takes time but saves more than it takes.

### Intention-Revealing Names
The name should answer all big questions. It should tell you why it exists, what it does, and how it is used. If the name requires a comment, the name does not reveal the intent.
```javascript
let d; // elapsed time in days
```
We should choose the name that specifies what is being measured and the unit of that measurement:
```javascript
let elapsedTimeInDays;
let daysSinceCreation;
let daysSinceModification;
let fileAgeInDays;
```
Example of code that is hard to understand because of using bad names:
```javascript
function getThem() {
    let list1 = [];
    for (let x in theList)
        if (x[0] == 4) list1.add(x);
    return list1;
}
```
The problem isn't the simplicity of the code but the *implicity* of the code. The code doesn't tell what kinds of things are in `theList` and what is the value of `4`. Just by giving concepts names, we can improve the code considerably:
```javascript
function getFlaggedCells() {
    let flaggedCells = [];
    for (let cell in gameBoard) {
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
    }
    return flaggedCells;
}
```
or in a functional way:
```javascript
function getFlaggedCells(gameBoard) {
    return gameBoard.filter(cell => cell[STATUS_VALUE] === FLAGGED)
}
```

**Example of Good and Bad Variable Names**

Purpose of Variable | Good Names | Bad Names
--- | --- | ---
Running total of checks written to date | `runningTotal`, `checkTotal` | `written`, `ct`, `checks`, `CHKTTL`, `x`, `x1`, `x2`
Velocity of a bullet | `velocity`, `trainVelocity`, `velocityMph` | `velt`, `v`, `tv`, `train`,`x`, `x1`, `x2`
Current date | `currentDate`, `todaysDate` | `cd`, `current`, `c`, `x`, `x1`, `x2`, `date`
Lines per page | `linesPerPage` | `lpp`, `lines`, `l`, `x`, `x1`, `x2`

**Optimum Name Length**

Too long | To short | Just Right
--- | --- | ---
`numberOfPeopleOnTheUsOlympicTeam` | `n`, `np`, `ntm` | `numTeamMembers`, `teamMemberCount`
`numberOfSeatsInTheStadium` | `n`, `ns`, `nsisd` | `numSeatsInStadium`, `seatCount`
`maximumNumberOfPointsInModernOlympics` | `m`, `mp`, `max`, `points` | `maxTeamPoints`, `maxPoints`

### Meaningful Distinctions
Because you can't use the same name to refer to two different things in the same scope, you might be tempted to change one name arbitrarily. It is not sufficient to add number series or noise words (redundant), even though the compiler or interpreter is satisfied.
```javascript
function copyChars(a1, a2) {
    for (let i = 0; i < a1.length; i++) {
        a2[i] = a1[i];
    }
}
```
If names must be different, then they should also mean something different. Number-series `{a1, a2, ... aN}` is the opposite of intentional naming. Such names are not disinformative--they are noninformative; they provide no clue to the author's intention. Consider:
```javascript
function copyChars(source, target) {
    for (let i = 0; i < source.length; i++) {
        target[i] = source[i];
    }
}
```
Use opposites precisely. Using naming conventions for opposites helps consistency, which helps readability.

**Common Opposites in Variable Names**
- begin/end
- first/last
- locked/unlocked
- min/max
- next/previous
- old/new
- opened/closed
- visible/invisible
- source/target
- up/down

### Pronounceable Names
If you can't pronounce it, you can't discuss it without sounding like an idiot. This matters because programming is a social activity. Compare:
```javascript
// ymdhms (date, year, month, day, hour)
let genymdhms;
let modymdhms;
let pszqint = "102";
```
to
```javascript
let generationTimestamp;
let modificationTimestamp;
let recordId = "102";
```

### Searchable Names
Single-letter names and numeric constants have a particular problem in that they are not easy to locate across a body of text. Single-letter names can ONLY be used as local variables inside short methods. The length of the name should correspond to the size of its scope. If a variable or constant might be seen or used in multiple places in a body of code, it is imperative to give it a search-friendly name. Compare:
```javascript
for (let j = 0; j < 34; j++) {
    s += (t[j] * 4) / 5;
}
```
to
```javascript
let realDaysPerIdealDay = 4;
const WORK_DAYS_PER_WEEK = 5;
let sum = 0;
for (let j = 0; j < NUMBER_OF_TASK; j++) {
    let realTaskDays = taskEstimate[j] * realDaysPerIdealDay;
    let realTaskWeeks = realTaskDays / WORK_DAYS_PER_WEEK;
    sum += realTaskWeeks;
}
```

### Naming Specific Types of Data
**Naming Loop Indexes**

The names `i`, `j`, and `k` are customary, simple loop variable names:
```javascript
for (let i = firstItem; i < lastItem; i++) {
    data[i] = 0;
}
```
If a variable is to be used outside the loop, it should be given a more meaningful name than `i`, `j`, `k`. For example, if you are reading records from a file and need to remember how many records you've read, a more meaningful name like `recordCount` would be appropriate:
```javascript
let recordCount = 0
while (moreScore()) {
    score[recordCount] = getNextScore();
    recordCount++;
}
```
One common reason loops grow is that they're nested. If you have several nested loops, assign longer names to the top variables to improve readability.
```javascript
for (teamIndex = 0; teamIndex < teamCount; teamIndex++) {
    for (eventIndex = 0; eventIndex < eventCount[teamIndex]; eventIndex++) {
        score[teamIndex][eventIndex] = 0;
    }
}
```
Carefully chosen names for loop-index variables avoid the common problem of index cross-talk. The simplest way to avoid such problems is simply to think of more descriptive names than `i`, `j`, `k`. The `score[teamIndex][eventIndex]` is more informative than `score[i][j]`

**Naming Status Variables**
Status variables describe the state of your program. It's better to think of flags as status variables. Flags should be assigned values and their values should be tested with enumerated types, named constants, or global variables that act as named constants. Here are some examples of flags with bad names:
```javascript
if (flag) ...
if (statusFlag == 0x0F) ...
if (printFlag == 16) ...
if (computeFlag == 0) ...

flag = 0x1;
statusFlag = 0x80;
printFlag = 16
computeFlag = 0;
```
Here are equivalent code example that are clearer:
```javascript
if (dataReady) ...
if (charType & PRINTABLE_CHAR) ...
if (reportType == reportTypeEnum.annual) ...
if (recalcNeeded == true) ...

dataReady = true;
charType = CONTROL_CHARACTER;
reportType = reportTypeEnum.annual
recalcNeeded = false;
```

**Naming Temporary Variables**

Temporary variables are used to hold intermediate results of calculations, as temporary placeholders, and to hold housekeeping values. They're usually called `temp`, `x`, or some other vague and nondescriptive name. In general, temporary variables are a sign that the programmer does not yet fully understand the problem. Moreover, because the variables are officially given `temporary` status, programmers tend to treat them more casually than other variables, increasing the chance of errors.
```javascript
let temp = Math.sqrt(b^2 - 4*a*c);
root[0] = (-b + temp) / (2 * a);
root[1] = (-b - temp) / (2 * a);
```
The name `temp` doesn't tell you anything about what the variable does. A better approach is shown in this example:
```javascript
let disciminant = Math.sqrt(b^2 - 4*a*c);
root[0] = (-b + disciminant) / (2 * a);
root[1] = (-b - disciminant) / (2 * a);
```

**Naming Boolean Variables**

Useful boolean variable names:
- **done**
- **error**
- **found**
- **success**

**Give boolean variables names that imply `true` or `false`**

Names like `done` and `success` are good boolean names because the state is either *`true`* or *`false`*. Names like `status` and `sourceFile`, on the other hand, are poor boolean names because they're not obviously *`true`* or *`false`*.

For better results, replace `status` with the name like `error` or `statusOK`, and replace `sourceFile` with `sourceFileAvailable` or `sourceFileFound`, or whatever the variable represents.

Some programmers like to put `Is` in front of their boolean names. Then the variable name becomes question: `isDone`? `isError`? `isFound`? `isProcessingComplete`? Answering the question with *`true`* or *`false`* provides the value of the variable.

**Use positive boolean variable names**

Negative names like `notFound`, `notDone`, and `notSuccessful` are difficult to read when they are negated.

**Naming Enumerated Types**

```javascript
const daysEnum = Object.freeze({
  monday: 0,
  tuesday: 1,
  wednesday: 2,
  thursday: 3,
  friday: 4,
  saturday: 5,
  sunday: 6
});
```
Taking this one step further, one could extract the logic into a function with a variable number of arguments and produce a frozen object. There is very little benefit to this technique, so a better alternative would be to create a simple class. After all, enums are more common in object-oriented programming languages, so this sounds like a great fit.

**Naming Constants**
When naming constants, name the abstract entity constant represents rather than the number the constant refers to. `FIVE` is a bad name for constant. `FIVE = 6` would be ridiculous. `CYCLES_NEEDED` is a good name. By the same token, `BAKERS_DOZEN` is also a poor constant name; `DONUT_MAX` is a good constant name.

## General Issues in Using Variable
### Disinformation
Programmers must avoid leaving false clues that obscure the meaning of code. We should avoid words whose entrenched meanings vary from our intended meaning. Abbreviations could be disinformative.

Do not refer to grouping accounts as an `accountList` unless it's a *`List`*. The word list means something specific to programmers. If the container holding the accounts is not a *`List`*, it may lead to false conclusions. So `accountGroup` or just plain `accounts` would be better.

A truly awful example of disinformative names would be the use of lower-case `L` and upper-case `O` as variable names, especially in combination. The problem, of course, is that they look almost entirely like constants one and zero, respectively.
```javascript
let a = l;
if (O == l) a = O1;
else l = 01;
```

**Problem-Orientation**

A good name mnemonic name generally speaks to the problem rather than the solution. A good name is the *what* more than *how*. In general, if a name refers to some aspect of computing rather than to the problem, it's a *how* rather than a *what*. Avoid such a name in favor of a name that refers to the problem itself.

A record of employee data could be called `inputRec` or `employeeData`. `inputRec` is a computer term that refers to computing ideas--input and record. `employeeData` refers to the problem domain rather than the computing universe. Similarly, for a bit field indicating printer status, `bitFlag` is a more computerish name than `printerReady`. In accounting application, `calcVal` is more computerish.

### Encodings
We have enough encodings to deal with without adding more to our burden. Encoding type or scope information into names simply adds an extra burden of deciphering. It is an unnecessary mental burden when trying to solve a problem. Encoded names are seldom pronounceable and are easy to miss-type. An encoding system will mislead the reader.

### Advice
- Avoid misleading names or abbreviations
- Avoid names with similar meanings
- Avoid variables with different meanings but similar names
- Avoid numerals in names
- Avoid misspelled words in names
- Don't differentiate variable names solely by capitalization
- Avoid multiple natural languages
- Avoid the names of standard types, variables, and routines
- Don't use a name that is unrelated to what the variable represents
- Avoid names containing hard-to-read characters

## Naming Conventions
**Why Have Convention?**
- They let you take more for granted. By making one global decision rather than many local ones, you can concentrate on the more important characteristics of code.
- They help you transfer knowledge across projects. Similarities names give you an easier and more confident understanding of what unfamiliar variables are supposed to do.
- They help you learn to code more quickly on a new project.
- They reduce name proliferation. Without naming conventions, you can easily call the same thing by two different names. For example, you might call total points both `pointTotal` and `totalPoints`.
- They compensate for language weaknesses. The convention can differentiate between local, class, and global data.
- They emphasize relationships among related items.

**When You Should Have a Naming Convention?**
- When multiple programmers are working on a project
- When you plan to turn the program over to another programmer for modification and maintenance
- When your programs are reviewed by other programmers in your organization
- When your program is so large that you can't hold the whole thing in your brain at once and must think about it in pieces
- When your program will be long-lived enough that you might put it aside for a few weeks or months before working on it again
- When you have a lot of unusual terms that are common on a project and want to have standard terms or abbreviations to use in coding

You always benefit from having some kind of naming convention. The considerations above should help you determine the extent of the convention to be on the particular project.

> The most important consideration in naming a variable is that the name fully and accurately describes the entity the variable represents.
> 
> Good variable names are a key element of program readability.

## Bibliography:
- Martin, R. C. (2009). Clean code: a handbook of agile software craftsmanship. Pearson Education.
- McConnell, S. (2004). Code complete. Pearson Education.

Thanks to Julien Dephix, Ben Sinclair, and other advisors who have helped improve this article.