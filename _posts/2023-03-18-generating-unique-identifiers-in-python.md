---
layout: post
date: 2023-03-18 00:00:00 +0100
tags: Python
categories: Software-Development Programming
title: 'Generating Unique Identifiers in Python'
---

Automating database processes are easy to do in Python. There are multiple packages allowing for interaction with different kinds of databases such as [SQLalchemy](https://www.sqlalchemy.org/). Thus we can place information from our other Python scripts directly into the appropriate databases through Python itself.

A common task is generating new unique identifiers for items in the databases. It is good practice to have an unique identifier that is separate from all other kind of data to ensure privacy. Of course it is possible to make unique identifiers by combining several pieces of information. However can it be guaranteed that those combinations will always be unique? What will be the effect if one of the subfields of information changes? Using a combination of information can lead to a whole can of worms of unforeseen issues.

Thus Universal Unique IDentifier's (UUIDs) are generally preferred for truly unique identifiers. They are also called General Unique IDentifier's (GUIDs). Python has a standard library (since Python 2.5) for generating UUID. This library provides four methods for generating UUID according to slightly different approaches.

```python
import uuid

unique_id_1 = uuid.uuid1()
unique_id_3 = uuid.uuid3(unique_id_1, "some_string")
unique_id_4 = uuid.uuid4()
unique_id_5 = uuid.uuid5(unique_id_1, "some_string")
```

The first method is `uuid1()`. This makes an identifier from the host ID, a sequence number, and the current time. The host ID comes basically from the device you are using. The sequence number is a random sequence number of 14 bits. Due to the host ID, it is technically possible to trace down by who the identifier is generated, which can be good or bad depending on your own requirements. 

The second method, named `uuid3()` (not 2), generates the UUID quite differently. For `uuid3()` you need to give a UUID and a string. Both are hashed together using the MD5 hash, resulting in a UUID. The string can be a standard string of your own choosing. Thus this method gives a bit more control on the resulting UUID as you can always supply the same values, which is great for reproducible and predictable UUIDs. The same goes for the method `uuid5()`, but uses SHA1 hash instead of the MD5 hash for generating the UUIDs.

Finally, `uuid4()` gives a completely random identifier. This is likely the best method if we want to use the UUID for anonymity and privacy concerns. If there are any concerns with the UUIDs you can always check if the generated UUID is already in the database, though I doubt that is an issue as long as the UUIDs are generated through the same method.
