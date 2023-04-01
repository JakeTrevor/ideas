# your Discord Accountant Bot (DAB)

commands:

| command    | args          | use                                                                 |
| ---------- | ------------- | ------------------------------------------------------------------- |
| /i-owe-u   | @user $amount | record the user who types this command as oweing $amount to @user   |
| /u-owe-me  | @user $amount | record the @user as oweing the person who typed the command $amount |
| /settle-up | @user         | generates payment link for the tab {@me @user}                      |
| /poke      | @user         | reminds the relevant party in the tab {@me @user} to pay their tab  |


| /display   | @user         | show how much the the user who types this owes @user                |


endpoints:

```ts
interface tabID {
	from: user
	to: user
} unique together from to

```

```ts
interface create_or_add_to_tab {
	from:   user
	to:     user
	amount: fin
} => tabID = {from, to}
```

```ts
type settle =
  | {
      tabs: tabID[];
    }
  | {
      all: True;
    };
```

```ts
type send {
	from: user
	to:   user
	amount: fin
}
```

```ts
interface poke {
  from: user;
  to: user;
}
```
