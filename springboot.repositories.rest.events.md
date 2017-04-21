# Spring data rest event


```bash
@RepositoryEventHandler 
public class PersonEventHandler {

  @HandleBeforeSave
  public void handlePersonSave(Person p) {
    // … you can now deal with Person in a type-safe way
  }

  @HandleBeforeSave
  public void handleProfileSave(Profile p) {
    // … you can now deal with Profile in a type-safe way
  }
  
    // BeforeCreateEvent

    // AfterCreateEvent

    // BeforeSaveEvent

    // AfterSaveEvent

    // BeforeLinkSaveEvent

    // AfterLinkSaveEvent

    // BeforeDeleteEvent

    // AfterDeleteEvent
}
```