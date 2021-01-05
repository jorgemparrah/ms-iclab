# Configuracion Laboratorio
Se debe crear un _Multibranch Pipeline Job_ con el repositorio URL: `https://github.com/jorgemparrah/ms-iclab.git`.
Y se deben agregar los siguientes behaviors:

### Behavior: Filter by name (with wildcars)
- Agregar un behavior _Filter by name (with wildcars)_
- Colocar en _Include_ el valor: `*`
- Colocar en _Exclude_ el valor: `*main *master`

### Behavior: Check out to matching local branch
- Agregar un behavior _Check out to matching local branch_

### Behavior: Specify ref specs
- Agregar un behavior _Specify ref specs_
- Colocar en el campo _Ref Spec_ el siguiente valor: `+refs/heads/*:refs/remotes/@{remote}/*`

***

# Getting Started
## Windows

### Compile Code
* ./mvnw.cmd clean compile -e

### Test Code
* ./mvnw.cmd clean test -e

### Jar Code
* ./mvnw.cmd clean package -e

### Run Jar
* Local:      ./mvnw.cmd spring-boot:run 
* Background: nohup bash mvnw.cmd spring-boot:run &

### Testing Application
* Abrir navegador: http://localhost:8080/rest/mscovid/test?msg=testing

## Linux

### Compile Code
* ./mvnw clean compile -e

### Test Code
* ./mvnw clean test -e

### Jar Code
* ./mvnw clean package -e

### Run Jar
* Local:      ./mvnw spring-boot:run 
* Background: nohup bash mvnw spring-boot:run &

### Testing Application
* curl -X GET 'http://localhost:8080/rest/mscovid/test?msg=testing'


# Jenkins Shared Libraries
- Jenkins Shared Libraries: https://www.jenkins.io/doc/book/pipeline/shared-libraries/

# Uso
- Agregar archivo **_Jenkinsfile_** en la raíz de la rama del proyecto a procesar (sólo como pivote al código del pipeline).
- Registrar Pipeline en **_Jenkins -> Administrar Jenkins -> Configuración Global -> Global Pipeline Libraries_** bajo el nombre **_pipeline_**
- Configurar _Multibranch Pipeline Job_ o _Pipeline Job_ en Jenkins con el repositorio del proyecto a procesar.