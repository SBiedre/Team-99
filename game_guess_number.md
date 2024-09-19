Game.java

```java
package com.datorium.Datorium.API;

public class Game {

    //1. Create a game where you have to guess a number.
    //2. If the number is too big, then we return 3
    //3. If the number is too small, we return 2
    //4. If the number is exactly the same, we return 1.

    private int randomNumber;

    public void setRandomNumber(int randomNumber) {
        this.randomNumber = randomNumber;
    }

    public int guessNumber(int guessedNumber) {
        if (guessedNumber > randomNumber) {
            return 3;
        } else if (guessedNumber < randomNumber) {
            return 2;
        } else {
            return 1;
        }
    }
}
```
GameTest.java

```java
package com.datorium.Datorium.API;

import org.junit.jupiter.api.Test;
import org.springframework.util.Assert;

public class GameTest {

    @Test
    public void WHEN_GuessIsTooBig_THEN_Return_3() {
        var game = new Game();
        game.setRandomNumber(5);

        var guess = game.guessNumber(50);

        Assert.isTrue(guess == 3, "It's supposed to return 3 when the guess is too big!");
    }

    @Test
    public void WHEN_GuessIsTooSmall_THEN_Return_2() {
        var game = new Game();
        game.setRandomNumber(25);

        var guess = game.guessNumber(15);

        Assert.isTrue(guess == 2, "It's supposed to return 2 when the guess is too small!");
    }

    @Test
    public void WHEN_GuessIsEqual_THEN_Return_1() {
        var game = new Game();
        game.setRandomNumber(10);

        var guess = game.guessNumber(10);

        Assert.isTrue(guess == 1, "It's supposed to return 1 when the guess is correct!");
    }

}
```
