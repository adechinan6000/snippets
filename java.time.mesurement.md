## Time mesurement

* sample

```bash
Instant b = Instant.now();
callOperationToTime();
Instant e = Instant.now();
Duration timeElapsed = Duration.between(b, e);
System.out.println("elapsed time ( milliseconds ):" +timeElapsed.toMillis());
```

* you can use for timeElapsed:
    - toNanos(), toMillis(), toMinutes(), toHours(), toDays()



## Period mesurement 

```bash
LocalDate sinceGraduation = LocalDate.of(1984, Month.JUNE, 4);
LocalDate currentDate = LocalDate.now();
Period betweenDates = Period.between(sinceGraduation, currentDate);
int diffInDays = betweenDates.getDays();
int diffInMonths = betweenDates.getMonths();
int diffInYears = betweenDates.getYears();
```