Para ejecutar correctamente mi API de PHP debe descargar Xampp, y en la carpeta C:\xampp\htdocs debe agregar la carpeta que se encuentra en este repositorio, ademas debe crear la sigueinte base de datos en MySQL Workbeanch 

CREATE DATABASE 'telastock'

CREATE TABLE 'rol' (
  'id' int(11) NOT NULL AUTO_INCREMENT,
  'nombre' varchar(50) NOT NULL,
  PRIMARY KEY ('id')
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

INSERT INTO 'telastock'.'rol'('id','nombre')
VALUES(1,'ADMINISTRADOR'),(2, 'ASESOR'),(3,'CLIENTE'),

CREATE TABLE 'usuarios' (
  'id' int(11) NOT NULL AUTO_INCREMENT,
  'nombre' varchar(50) NOT NULL,
  'apellido' varchar(50) NOT NULL,
  'email' varchar(100) NOT NULL,
  'contraseña' varchar(255) NOT NULL,
  'rol_id' int(11) NOT NULL,
  'fecha_registro' timestamp NOT NULL DEFAULT current_timestamp(),
  PRIMARY KEY ('id'),
  UNIQUE KEY 'email' ('email'),
  KEY 'fk_usuarios_rol' ('rol_id'),
  CONSTRAINT 'fk_usuarios_rol' FOREIGN KEY ('rol_id') REFERENCES 'rol' ('id')
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
