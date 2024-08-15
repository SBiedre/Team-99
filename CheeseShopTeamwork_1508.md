![AddCheeese](https://github.com/SBiedre/Team-99/blob/main/addCheese.png?raw=true)
![UpdateCheese](https://github.com/SBiedre/Team-99/blob/main/updateCheese.png?raw=true)
![GetCheese](https://github.com/user-attachments/assets/1adb6eff-fe55-4db6-b4a0-fe338dd13dd5)



Cheese
```java
package com.datorium.Datorium.API.DTOs;

public class Cheese {
    public String name;
    public int price;
    public int quantity;
}
```

UpdateCheeseDTO

```java
package com.datorium.Datorium.API.DTOs;

public class UpdateCheeseDTO {
    public Cheese cheese;
    public int price;
    public int quantity;
}
```
CheeseShopController

```java
package com.datorium.Datorium.API.Controllers;


import com.datorium.Datorium.API.DTOs.Cheese;
import com.datorium.Datorium.API.DTOs.UpdateCheeseDTO;
import com.datorium.Datorium.API.Services.CheeseShopService;
import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;

@RestController
@RequestMapping("/cheese")
public class CheeseShopController {

    private CheeseShopService cheeseShopService;
    public CheeseShopController() {
        cheeseShopService = new CheeseShopService();
    }


    @PostMapping("/add")
    public int add(@RequestBody Cheese cheese) {
        return cheeseShopService.add(cheese);

    }

    @GetMapping("/getCheese")
    public ArrayList<Cheese> getCheese() {
        return cheeseShopService.getCheeses();
    }

    @PostMapping("/update")
    public Cheese update(@RequestBody UpdateCheeseDTO updateCheeseDTO) {
        return cheeseShopService.update(updateCheeseDTO.price, updateCheeseDTO.quantity, updateCheeseDTO.cheese);
    }
}
```

CheeseShopService

```java
package com.datorium.Datorium.API.Services;
import com.datorium.Datorium.API.DTOs.Cheese;
import com.datorium.Datorium.API.Repo.CheeseShopRepository;


import java.util.ArrayList;

public class CheeseShopService {

    private CheeseShopRepository cheeseShopRepository;
    public CheeseShopService(){
        cheeseShopRepository = new CheeseShopRepository();
    }
    public int add(Cheese cheese) {
        return cheeseShopRepository.add(cheese);
    }

    public ArrayList<Cheese> getCheeses() {
        return cheeseShopRepository.getCheeses();
    }

    public Cheese update(int price, int quantity, Cheese updateCheeseDTO){
        return cheeseShopRepository.update(price, quantity, updateCheeseDTO);
    }

}
```

CheeseShopRepository

```java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTOs.Cheese;

import java.util.ArrayList;

public class CheeseShopRepository {


    private ArrayList<Cheese> cheeses = new ArrayList<>();

    public int add(Cheese cheese){
        cheeses.add(cheese);
        return cheeses.size();
    }

    public ArrayList<Cheese> getCheeses(){
        return cheeses;
    }

    public Cheese update(int price, int quantity, Cheese updateCheeseDTO){
        for (Cheese cheese : cheeses) {
            if (cheese.name.equals(updateCheeseDTO.name)) {
                cheese.price = price;
                cheese.quantity = quantity;
                return cheese;
            }
        }
        return null;  // Return null or throw an exception if the cheese is not found
    }
}
```
