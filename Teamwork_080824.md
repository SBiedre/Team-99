
MessageController
```java
package com.datorium.Datorium.API.Controllers;


import com.datorium.Datorium.API.DTOs.Message;
import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Services.MessageService;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/user")
public class MessageController {

    private MessageService messageService;
    public MessageController() {
        this.messageService = new MessageService();

    }

    @PostMapping("/sendMessage")
    public String sendMessage(@RequestBody Message message) {
        return messageService.sendMessage(message.getMessage());
    }

}
```

Message

```java
package com.datorium.Datorium.API.DTOs;

public class Message {
    private String message;

    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }
}
```
MessageService

```java
package com.datorium.Datorium.API.Services;


import org.springframework.stereotype.Service;

@Service
public class MessageService {

    public String sendMessage(String message) {
        return "Message received: " + message;
    }
}
```
![scrnsht](https://github.com/user-attachments/assets/a0b98acf-feb0-49f4-865a-7ac0f9bb08b4)
