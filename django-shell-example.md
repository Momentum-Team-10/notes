# How to create a related object in the Django console

```sh
❯ python manage.py shell
Python 3.10.0 (default, Oct 25 2021, 10:03:15) [Clang 13.0.0 (clang-1300.0.29.3)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from contacts.models import Contact, Note
>>> contact = Contact.objects.get(name="Belletrix")
>>> contact
<Contact: Belletrix>
>>> contact.notes # observe what this returns
<django.db.models.fields.related_descriptors.create_reverse_many_to_one_manager.<locals>.RelatedManager object at 0x111781ff0>
>>> contact.notes.all() # to query for the related objects we need to use `all()`
<QuerySet []>
>>> new_note = Note(text="This is my dog.", contact=contact)
>>> new_note
<Note: This is my dog.>
>>> new_note.contact
<Contact: Belletrix>
>>> new_note.save() # this is what writes the record to the database
>>> new_note.pk # only after it is saved does it have a pk!
1
```
