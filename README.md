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


select * from actor;
select * from director;
select * from movies;
select * from moviecast;
select * from rating;

insert into actor values('ACT001','Jenna Ortega','F');
insert into actor values('ACT002','Hanna Harrington','F');
insert into actor values('ACT003','George Boston','M');
insert into actor values('ACT004','Harry Wills','M');
insert into actor values('ACT005','Scarlet Witch','F');
insert into actor values('ACT006','Alex Bills','M');
insert into actor values('ACT007','Amy Mendes','F');
insert into actor values('ACT008','Shaun Pills','M');
insert into actor values('ACT009','Sanith Martinez','M');
insert into actor values('ACT010','Chris Holmes','M');

insert into director values('DIR0001','Shaun Paul',948141548);
insert into director values('DIR0002','Sanith Shet',814154548);
insert into director values('DIR0003','Sheetal Shen',457012234);
insert into director values('DIR0004','Shreenidhi',473125489);
insert into director values('DIR0005','Rashwin Ven',145641548);
insert into director values('DIR0006','Sankalp Nayak',123489788);
insert into director values('DIR0007','Christoper Paul',678945218);
insert into director values('DIR0008','Sam Soares',814503215);

insert into movies values('MOV_001','Wednesday','2022','Eng','DIR0001');
insert into movies values('MOV_002','Black Adams','2022','Hindi','DIR0003');
insert into movies values('MOV_003','Interstellar','2017','Eng','DIR0007');
insert into movies values('MOV_004','Man from Toronto','2018','Eng','DIR0006');
insert into movies values('MOV_005','Get Out','2020','Kannada','DIR0005');
insert into movies values('MOV_006','Top Gun','2022','Eng','DIR0001');
insert into movies values('MOV_007','Parallel Mothers','2021','Eng','DIR0004');
insert into movies values('MOV_008','Marriage Story','2019','Eng','DIR0002');
insert into movies values('MOV_009','Nobody','2018','Arabic','DIR0008');
insert into movies values('MOV_010','Wrath of Man','2020','Eng','DIR0007');

insert into moviecast values('ACT004','MOV_008','Villain');
insert into moviecast values('ACT001','MOV_001','Witch');
insert into moviecast values('ACT010','MOV_004','Hero');
insert into moviecast values('ACT004','MOV_008','Actor');
insert into moviecast values('ACT005','MOV_007','Ghost');
insert into moviecast values('ACT003','MOV_006','Pilot');
insert into moviecast values('ACT007','MOV_003','Astronaut');
insert into moviecast values('ACT009','MOV_010','Villain');
insert into moviecast values('ACT002','MOV_009','Actress');
insert into moviecast values('ACT008','MOV_002','SuperMan');

insert into rating values('MOV_001',5);
insert into rating values('MOV_002',3);
insert into rating values('MOV_003',3);
insert into rating values('MOV_004',1);
insert into rating values('MOV_005',4);
insert into rating values('MOV_006',3);
insert into rating values('MOV_007',3);
insert into rating values('MOV_008',4);
insert into rating values('MOV_009',2);
insert into rating values('MOV_010',1);

--1.List the titles of all movies directed by 'Sanith Shet'

select m.Movie_title
from movies as m,director as d
where d.Director_ID=m.Director_ID and d.Director_Name='Sanith Shet';








