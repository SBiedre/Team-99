
![GetUsers](https://github.com/SBiedre/Team-99/blob/main/getUsers.png?raw=true)

User

```java
package com.datorium.Datorium.API.DTOs;

public class User {
    public String name;
}
```

UserController
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Services.UserService;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/user")
public class UserController {

    private UserService userService;
    public UserController() {
       userService = new UserService();

        //This code runs first, when creating UserController object

    }

    //CRUD
    //AddUser
    //UpdateUser
    //GetUser
    //DeleteUser

    @PostMapping("/add")
    public int add(@RequestBody User user) {
        return userService.add(user);

    }

    @GetMapping("/getUsers")
    public List<User> getUsers() {
        return userService.getUsers();
    }

}
```

UserService

```java
package com.datorium.Datorium.API.Services;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Repo.UserRepo;

import java.util.Arrays;
import java.util.List;

public class UserService {
    private UserRepo userRepo;
    public UserService(){
        userRepo = new UserRepo();
    }
    public int add(User user) {
        return userRepo.add(user);
    }

    public List<User> getUsers() {
        return userRepo.getUsers();
    }

}
```
UserRepo

```java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTOs.User;

import java.util.ArrayList;
import java.util.List;

public class UserRepo {

    private ArrayList<User> users = new ArrayList<>();

    public int add(User user){
        users.add(user);
        return users.size();
    }

    public List<User> getUsers(){
        return users;
    }


}
```



