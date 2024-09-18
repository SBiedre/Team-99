MathService.java

```java
package com.datorium.Datorium.API;

public class MathService {

    public int sum(int a, int b) {
        int sum = a + b;
        if (sum > 100){
            return 0;
        }
        return sum;
    }
}
```
Main.java

```java
package com.datorium.Datorium.API;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DatoriumApiApplication {

	public static void main(String[] args) {
		var mathService = new MathService();
		System.out.println("The sum of 50 + 60 is: " + mathService.sum(50, 60));

		SpringApplication.run(DatoriumApiApplication.class, args);
	}

}
```
DatoriumApiApplicationTests.java

```java
package com.datorium.Datorium.API;

import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.util.Assert;

@SpringBootTest
class DatoriumApiApplicationTests {

	@Test

	void WHEN_sumIsBelow100_THEN_ResultIsSum(){
		var mathService = new MathService();

		var sum = mathService.sum(50, 25);

		Assert.isTrue(sum==75, "Hey the sum is below 100");
	}

	void WHEN_sumIsAbove100_THEN_ResultIsZero(){
		var mathService = new MathService();

		var sum = mathService.sum(50, 60);

		Assert.isTrue(sum==0, "Hey the sum is above 100");
	}

	void WHEN_sumIsEqual100_THEN_ResultIsSum(){
		var mathService = new MathService();

		var sum = mathService.sum(50, 50);

		Assert.isTrue(sum==100, "Hey the sum is equal 100");
	}




}

```
