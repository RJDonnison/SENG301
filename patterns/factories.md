# Factory Method vs Abstract Factory

| Aspect           | Factory Method                                 | Abstract Factory                                             |
| ---------------- | ---------------------------------------------- | ------------------------------------------------------------ |
| **Intent**       | Create **one** object, subclasses decide which | Create **families** of related objects                       |
| **Products**     | Single product type                            | Multiple related products                                    |
| **Client knows** | Abstract creator                               | Abstract factory interface only                              |
| **Structure**    | Inheritance — override the factory method      | Composition — swap the factory object                        |
| **Main con**     | Subclass explosion per new variant             | Adding a new product type breaks the whole factory interface |

> **One-liner:** Factory Method = _which single object?_ via subclassing. Abstract Factory = _which family?_ via a swappable factory.
