### Introduction
This library is designed to generate unique, complex passwords for different resources with one universal password.

This library does not store passwords in memory, but only generates passwords based on input parameters.
At the moment, the distribution of characters in the password is not perfect, but in General it is a trifle and does not greatly affect the security.

### How it works?

It works pretty simple. It is enough to initialize this library and pass 3 parameters to the input:
- resource name
- login
- your universal password

And at the output you will receive the generated password

### What it looks like in the code?

```js
MyPassword = PasswordComplicate();
var googlePassword = MyPassword.generate('google.com', 'login', 'password');
var yandexPassword = MyPassword.generate('yandex.ru' , 'login', 'password');

console.log(googlePassword); // v1_$twq9e9xaH4liClHumOsjeVGGQfNioxhq
console.log(yandexPassword); // v1_$BvPMnpQhNXzmIX1NUqjisSPax3CInFPQ

```

### Security
In this example, to pick up the generated password according to the resource https://password.kaspersky.com/ru/ :
```
To choose your password 
on a normal computer, you will need
10000+CENTURIES
```

Remember that in the beginning we had a simple password that you can choose manually.

### Paranoid security
Alas, as practice shows, it is almost impossible to remember a thousand passwords. 
According to this data, the password has to be stored somewhere in a file that eventually turns to mush.
And the loss of this file becomes a disaster, and theft ... .
A logical security question, if a person has learned your password, now he can enter anywhere...
In fact, Yes (the output is in "Even more security), this is a minus of this library, but it is better than one universal password for all used resources.

### Even more security
Are you paranoid and want even more security? 
We place this library on the resource access to which is carried out only by login and password and only by you.
I'm sure it will be a separate username (not admin) and password (not 123456).
Next, create a config for this library
```js
var conf = {
  sol: 'ABRA_KADABRA',
  prefix: 'u&882_a1',
  suffix: '*#2',
  passSymbol: 'de2VWX345fghiabcOPQRSTUjklmnoABCD167EFGHIJKpqrstuvwxyzLMNYZ890',
}
```

Well almost all (do not forget your config)
```js
var conf = {
  sol: 'ABRA_KADABRA',
  prefix: 'u&882_a1',
  suffix: '*#2',
  passSymbol: 'de2VWX345fghiabcOPQRSTUjklmnoABCD167EFGHIJKpqrstuvwxyzLMNYZ890',
}
MyPassword = PasswordComplicate(conf);
var googlePassword = MyPassword.generate('google.com', 'login', 'password');
var yandexPassword = MyPassword.generate('yandex.ru' , 'login', 'password');

console.log(googlePassword); // u&882_a1zdk7e5hz01upAfs0fedrwlW8WBF8aAdz*#2
console.log(yandexPassword); // u&882_a1QNWnMfwr3jHyr87Z6RZbhAHUCAZCCvl0*#2
```
