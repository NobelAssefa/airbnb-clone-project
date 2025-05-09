**We have 6 main entities:**
User
Property
Booking
Payment
Review
Message

**Relationships**
User → Property: One-to-Many (a host can own many properties)
User → Booking: One-to-Many (a guest can book many times)
Property → Booking: One-to-Many (a property can have many bookings)
Booking → Payment: One-to-One (a booking has one payment)
Property + User → Review: Many-to-Many resolved via the Review table (one user can review many properties)
User ↔ User → Message: Many-to-Many self-relationship (user sends messages to other users)

**Link to Er Diagram**

https://drive.google.com/file/d/1V8eHlDEdyfw3uiZIJL0Yyj18TtdWRlGR/view?usp=sharing
