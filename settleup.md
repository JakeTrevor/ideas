# your Discord Accountant Bot (DAB)

commands:

| command   | args           | use                                     |
| --------- | -------------- | --------------------------------------- |
| /settleup | -              | generates payment link                  |
| /iowe     | @user $amount  | record @me as owing $amount to @user    |
| /iamowed  | $amount @users | record @users as owing @me $amount each |
| /account  | -              | paste                                   |

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
type settle  = { 
	tabs: tabID[];
} | {
	all: True;
}
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
	from: user
	to: user
}
```

housekeeper:
auto clean tabs;
i.e. i owe ash 20
ash owes me 10

so ash owes me nothing and I owe ash 10