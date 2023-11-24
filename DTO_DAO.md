https://stackoverflow.com/questions/14366001/dto-and-dao-concepts-and-mvc
DTO is an abbreviation for Data Transfer Object, so it is used to transfer the data between classes and modules of your application.

DTO should only contain private fields for your data, getters, setters, and constructors.
DTO is not recommended to add business logic methods to such classes, but it is OK to add some util methods.
DAO is an abbreviation for Data Access Object, so it should encapsulate the logic for retrieving, saving and updating data in your data storage (a database, a file-system, whatever).

Here is an example of how the DAO and DTO interfaces would look like:

interface PersonDTO {
    String getName();
    void setName(String name);
    //.....
}

interface PersonDAO {
    PersonDTO findById(long id);
    void save(PersonDTO person);
    //.....
}