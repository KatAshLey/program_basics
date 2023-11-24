# set up
# install example database. follow link and download ready to use link
https://github.com/bradleygrant/sakila-sqlite3

# install SQLite - only need to do this once
https://www.sqlite.org/download.html#:~:text=sqlite%2Dtools%2Dwin%2Dx64%2D3440000.zip
download this file sqlite-tools-win-x64-3440000.zip(4.71 MiB)	

# on computer
settings >> system >> about >> advanced system settings >> Environmental Variables >> choose PATH >> Edit >> New >> choose sqlite extracted folder Path = C:/sqlite

# install vs code extension,
database client

# create new connection with database file
left menu >> 3 dots >> database >> + >> SQLite >> enter path to database file >> connect


# =====================================================================


# views all columns from actor table.  max 10 lines
# can call certain columns, use title and , to separate columns
SELECT * FROM actor LIMIT 10

# run call
ctrl + enter

# comment out calls
-- 

# returns unique items in rating column
SELECT DISTINCT rating FROM film

# returns the count of ratings, grouped by ratings eg g -478, pg-78, r-189
SELECT rating, count(*) FROM film GROUP BY rating

# returns all G rating movies
SELECT * FROM film WHERE rating = 'G'

# returns films, g rating, ordered by rental duration in descending order
SELECT * FROM film WHERE rating = 'G' ORDER BY rental_duration DESC

# returns list of g and pg movies
SELECT * FROM film WHERE rating = 'G' OR rating = 'PG'

# returns joint list film and language where language is specified and pg rating
SELECT film.title, language.name, film.rating
FROM film
JOIN language
WHERE film.language_id = language.language_id AND film.rating = 'PG'

# insert single item into table
INSERT INTO actor
VALUES (201, 'BARRY', 'ALLEN', time());

# insert multiple items into table
INSERT INTO actor
VALUES 
    (201, 'BARRY', 'ALLEN', time()),
    (202, 'JOHN', 'DOE', time());

# search for inserted item above
SELECT * FROM actor WHERE actor_id = 201

# multiple calls use ;
# make sure the current calls are always at the bottom, commented out code at the top otherwise code will continue to run and not show anything

# to update an existing entry
UPDATE actor
SET first_name = 'WALLY', last_name='WEST', last_update=TIME()
WHERE actor_id = 201

# to delete an entry that matches actor_id
DELETE from actor
WHERE actor_id = 10

# ###############last_updated is very important, also use first_created

# gives table information
PRAGMA table_info(actor)

# to make limit work
PRAGMA SQLITE_ENABLE_UPDATE_DELETE_LIMIT=ON

# alternate ways for time entries in
TIMESTAMP()
CURRENT_TIMESTAMP()


# ===================================================================

# sqlmodel is based off sql alchemy

# trying to get pydantics upgraded to use sqlmodel.  This did not work.
python -m pip install --upgrade pydantic
pip install --upgrade --force-reinstall sqlmodel fastapi[api]


# python and sql.  Make sure to use a virtual environment
from typing import Optional
from sqlmodel import Field, SQLModel

# class definition of a hero
class Hero(SQLModel, table=True):
    id: Optional[int] = Field(default=None, primary_key=True)
    name: str
    secret_name: str
    age: Optional[int] = None


# primary keys are unique to the table, is index(fast to look up. so if you want to look up tables using this then make it a index)
compound key, using 2 coloumns as index



# example of python sqlite
# import sqlmodel 
from sqlmodel import Field, Session, SQLModel, create_engine, select

# defines hero data
hero_1 = Hero(name="Deadpond", secret_name="Dive Wilson")
hero_2 = Hero(name="Spider-Boy", secret_name="Pedro Parqueador")
hero_3 = Hero(name="Rusty-Man", secret_name="Tommy Sharp", age=48)

# creates engine object that handles communication with the database.  Includes URL for the database to use.  Be aware of 3 /// in path.
# add echo=True in parameters to make the engine print all sql statements it executes.  Good for debugging/testing.  Remove for production
engine = create_engine("sqlite:///database.db")

# creates database and table
SQLModel.metadata.create_all(engine)

# creates connection to add data
with Session(engine) as session:  
    session.add(hero_1)
    session.add(hero_2)
    session.add(hero_3)
    session.commit()


# search table to find entry
    with Session(engine) as session:
    statement = select(Hero).where(Hero.name == "Spider-Boy")
    hero = session.exec(statement).first()
    print(hero)

# gives all versions of entry SPIDER-BOY. returns list
    with Session(engine) as session:
    statement = select(Hero).where(Hero.name == "Spider-Boy")
    heroes = session.exec(statement).all()
    print(heroes)


# ============================================================


# 23 Nov
# normalization is joining tables (sql). denoramlization (nosql), means you have to update lots, info is with the original record.

# foreign keys. table has to be created before foreign key can be used.

# if deleting a record with foreign keys used in other tables, ensure that all connections/foreign keys have been removed from other records first.

# create type hint for FAST API for SQL, put in the @app line(,here)
response_model=Hero

# in url use hyphen rather than underscore

# used to update hero information, use api below, DTO
class HeroUpdate(SQLModel):
    name: Optional[str] = None
    secret_name: Optional[str] = None
    age: Optional[int] = None

# api to change hero information using patch
@app.patch("/heroes/", response_model=Hero)
def change_secret_name(hero_update: HeroUpdate):
    with Session(engine) as session:
        db_hero = session.exec(
            select(Hero).where(Hero.name == hero_update.name)
        ).first()
        if not db_hero:
            raise HTTPException(status_code=404, detail="Hero not found")
        hero_data = hero_update.dict(exclude_unset=True)
        for key, value in hero_data.items():
            setattr(db_hero, key, value)
        session.add(db_hero)
        session.commit()
        session.refresh(db_hero)
        return db_hero
# testing using postman use dropdown patch, enter url/heroes/ give {hero data} in body >> raw >> json

# builds a new Session each time it is called.  dont have to call with session(engine) in each definition
def get_session():
    with Session(engine) as session:
        yield session

# to use above session
def create_hero(*, session: Session = Depends(get_session), hero: HeroCreate):

# always turn on database backups, incremental or differential
# test code properly to make sure you are only changing what you need, no accidental column deletes

# limit showing the max returns otherwise it takes too long, eg only first 100 entries, per page
offset: int = 0,
limit: int = Query(default=100, le=100),

# to turn on foreign key relationships
PRAGMA foreign_keys=ON

# when using foreign keys, in code try catch for making sure the foreign key exists(search for it) before using it.  

# right click table >> SQL Template >> insert to use a template, can use the execute button between code to run