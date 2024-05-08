Para ejecutar correctamente mi API de PHP debe descargar Xampp, y en la carpeta C:\xampp\htdocs debe agregar la carpeta que se encuentra en este repositorio, ademas debe crear la sigueinte base de datos en MySQL Workbeanch 

CREATE DATABASE 'telastock' <br>

CREATE TABLE 'rol' (<br>
  'id' int(11) NOT NULL AUTO_INCREMENT,<br>
  'nombre' varchar(50) NOT NULL,<br>
  PRIMARY KEY ('id')<br>
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;<br>
<br><br>
INSERT INTO 'telastock'.'rol'('id','nombre')<br>
VALUES(1,'ADMINISTRADOR'),(2, 'ASESOR'),(3,'CLIENTE'),<br>
<br><br>
CREATE TABLE 'usuarios' (<br>
  'id' int(11) NOT NULL AUTO_INCREMENT,<br>
  'nombre' varchar(50) NOT NULL,<br>
  'apellido' varchar(50) NOT NULL,<br>
  'email' varchar(100) NOT NULL,<br>
  'contraseña' varchar(255) NOT NULL,<br>
  'rol_id' int(11) NOT NULL,<br>
  'fecha_registro' timestamp NOT NULL DEFAULT current_timestamp(),<br>
  PRIMARY KEY ('id'),<br>
  UNIQUE KEY 'email' ('email'),<br>
  KEY 'fk_usuarios_rol' ('rol_id'),<br>
  CONSTRAINT 'fk_usuarios_rol' FOREIGN KEY ('rol_id') REFERENCES 'rol' ('id')<br>
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;<br>
