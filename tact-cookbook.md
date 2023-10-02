# Tact Cookbook

The core reason for creating the Tact Cookbook is to collect all the experience from Tact developers in one place so that future developers will use it!

Compared to the FunC Documentation, this article is more focused on everyday tasks every FunC developer resolve during the development of smart contracts.

## Basics
### How to write a Hello World smart contract

```
contract HelloWorld {

    get fun greeting(): String {
        return "hello world";
    }        

}
```

### How to write an 'if' statement in Tact

Tact supports if statements in a similar syntax to most programming languages. Curly braces are required though, so you can't leave them out.

The condition of the statement can be any boolean expression.

There is no switch statement in Tact. If you need to need to handle a group of outcomes separately, follow the else if patten you can see in the third example.

```
contract IfStatements {

    temperature: Int as int32;

    init() {
        self.ki = 9001;
    }

    receive("check1") {
        if (self.ki > 10) {
            dump("Your power level is larger than 10, not bad for a human");
        }
    }

    receive("check2")  {
        if (self.ki > 100) {
            dump("Your power level is larger than 100, Master Roshi is proud of you");
        } else {
            dump("Your Power Level is smaller than 100, still you have some potential");
        }
    }

    receive("check3") {
        if (self.ki > 9000) {
            dump("IT'S OVER 9000!");
        } else if (self.ki > 500) {
            dump("between 500 and 1000 - are you a half-breed Saiyan?");
        } else {
            dump("Your Power Level is smaller than 500, still you have some potential");
        }
    }
}
```