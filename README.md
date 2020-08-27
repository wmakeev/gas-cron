# gas-cron

- [croner](https://github.com/Hexagon/croner)

## Pattern

```
┌────────────── minute (0 - 59)
│ ┌──────────── hour (0 - 23)
│ │ ┌────────── day of month (1 - 31)
│ │ │ ┌──────── month (1 - 12)
│ │ │ │ ┌────── day of week (0 - 6)
│ │ │ │ │       (0 to 6 are Sunday to Saturday; 7 is Sunday, the same as 0)
│ │ │ │ │
* * * * *
```

## Usage

```ts
const expression = '*/30 2-22 * * *'

const cron: Cron.CronPattern = Cron.parse(expression)

const next1: Date = cron.next() // next scheduled date from now
const next2: Date = cron.next(new Date(2010, 0, 1)) // next scheduled date from some date

const next3: number = cron.msToNext()
const next4: number = cron.msToNext(new Date(2010, 0, 1))
```
