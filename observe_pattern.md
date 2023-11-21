# Observer Pattern

**Observer** is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

**Subject:** The object that has some interesting state is often called subject.

**publisher:** Subject's also going to notify other objects about the changes to its state, called publisher. 

**subscribers:** All other objects that want to track changes to the publisher’s state are called subscribers.

**The Observer pattern suggests:**
- Add a subscription mechanism to the publisher class
- So individual objects can subscribe to or unsubscribe from a stream of events coming from that publisher.

**To implement the pattern, you need to:**
- An array field for storing a list of references to subscriber objects.
- Several public methods which allow adding subscribers to and removing them from that list.
- Now, whenever an important event happens to the publisher, it goes over its subscribers and calls the specific notification method on their objects.


### Example:

```python
# event.py
from collections import defaultdict

subscribers = defaultdict(list) # Default value of the dictionary will be list

def subscribe(event_type: str, fn):
    subscribers[event_type].append(fn)

def post_event(event_type: str, data):
    if not event_type in subscribers:
        return
    for fn in subscribers[event_type]:
        fn(data)

# email_listener.py
from .event import subscribe

def handle_user_registered_event(user):
    send_email(user.email, "Welcome!")

def setup_email_event_handlers():
    subscribe("user_registered", handle_user_registered_event)

# log_listener.py
from .event import subscribe

def handle_user_registered_event(user):
    log(f"User registered with email address {user.email}")

def setup_log_event_handlers():
    subscribe("user_registered", handle_user_registered_event)

# user.py
from event import post_event

class User:
    def __init__(self, email: str, password: str):
        self.email = email
        self.password = password

    @classmethod
    def create(cls, email: str, password: str):
        user = cls(email, password)
        post_event("user_registered", user) # post an event
        return user

# main.py
from log_listener import setup_log_event_handlers
from email_listener import setup_email_event_handlers
from user import User

setup_email_event_handlers()
setup_log_event_handlers()
User.create(email="john@gmail.com", password="123456")
```
In this example, we have a `User` class that represents a user in our application. When a new user is created, we want to send a welcome email to the user and log the event. We can use the Observer Pattern to implement this functionality.

In the `event.py` file, we have a `subscribe` function that takes an event type and a callback function. The `subscribe` function adds the callback function to the list of subscribers for the given event type. The `post_event` function takes an event type and some data and calls all the callback functions that are subscribed to that event type with the given data.

In the `email_listener.py` file, we have a `handle_user_registered_event` function that takes a user object and sends a welcome email to the user. The `setup_email_event_handlers` function calls the `subscribe` function to subscribe the `handle_user_registered_event` function to the `user_registered` event.

In the `log_listener.py` file, we have a `handle_user_registered_event` function that takes a user object and logs the event. The `setup_log_event_handlers` function calls the `subscribe` function to subscribe the `handle_user_registered_event` function to the `user_registered` event.

In the `user.py` file, we have a `User` class that represents a user in our application. The `User` class has a `create` class method that takes an email and a password and creates a new user. The `create` method calls the `post_event` function to post the `user_registered` event with the user object.

In the `main.py` file, we call the `setup_email_event_handlers` function to subscribe the `handle_user_registered_event` function to the `user_registered` event. We also call the `setup_log_event_handlers` function to subscribe the `handle_user_registered_event` function to the `user_registered` event. Finally, we call the `User.create` method to create a new user. This will post the `user_registered` event with the user object. The `handle_user_registered_event` function will be called with the user object and it will send a welcome email to the user and log the event.



```python
@dataclass
class SomeObject:
    attr1: str
    attr2: str

    def __post_init__(self):
        post_event("object_created", self)
```