## ``` Movie_Database ```

create database my_movie_database;
use my_movie_database;


--Table : Actor
create table actor(
Actor_ID varchar(10) primary key,
Actor_Name varchar(20),
Actor_Gender varchar(10)
);

--Table : Director

create table director(
Director_ID varchar(10) primary key,
Director_Name varchar(20),
Director_Phone int
);

--Table : Movies

create table movies(
Movie_ID varchar(10) primary key,
Movie_Title varchar(30),
Movie_Year int,
Movie_Lang varchar(10),
Director_ID varchar(10)
);

--Table : Moviecast

create table moviecast(
Actor_ID varchar(10),
Movie_ID varchar(10),
Role varchar(20)
);

--Table : Rating

create table rating(
Movie_ID varchar(10),
Review_Star int
);


--ASSIGNING FOREIGN KEYS TO THE TABLES


--Movies(Director_ID)----> Director(Director_ID)

alter table movies add foreign key(Director_ID) references Director(Director_ID);

--Moviecast(Actor_ID)---->Actor(Actor_ID)

alter table moviecast add foreign key(Actor_ID) references Actor(Actor_ID);

--Moviecast(Movie_ID)---->Movies(Movie_ID)

alter table moviecast add foreign key(Movie_ID) references Movies(Movie_ID)

--Rating(Movie_ID)---->Movies(Movie_ID)

alter table rating add foreign key(Movie_ID) references Movies(Movie_ID);

