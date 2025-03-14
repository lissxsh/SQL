# SQL
CEITIGIRLS
CREATE DATABASE Colegiu
USE  Colegiu
CREATE TABLE Grupa(
		id_grupa INT IDENTITY(1,1) PRIMARY KEY,
		nume NVARCHAR(10) NOT NULL,
		an TINYINT ,
		id_profesor INT REFERENCES Profesor(id_profesor),
		id_spec TINYINT REFERENCES Spec(id_spec) 
		 )


CREATE TABLE Spec(
		id_spec INT IDENTITY(1,1) PRIMARY KEY,
		nume NVARCHAR(60) UNIQUE )

CREATE TABLE Student (
		 id_student INT IDENTITY(1,1),
		 nume NVARCHAR(50) NOT NULL,
		 prenume NVARCHAR(50) NOT NULL,
		 patrimonic NVARCHAR(50) NOT NULL,
		 sex NVARCHAR(1) CHECK (sex ='M' or sex='F')
		 d_nasteri DATE NOT NULL
		 tel NVARCHAR(9) CHECK( tel>0 and tel LIKE '0%' )
		 id_grupa INT REFERENCES Grupa(id_grupa)
		 id_loc INT REFERENCES Localitate(id_loc)  )

CREATE TABLE ObjStud (
    IdObjStud INT PRIMARY KEY,
    NmObjStud NVARCHAR(50) NOT NULL,
    id_cad INT REFERENCES Catedre(id_cad)
);






