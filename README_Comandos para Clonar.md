Para clonar este repositorio se debe ejecutar el siguiente comando:

git clone --recurse-submodules https://github.com/GrietM/ChallengeJS_Alkemy

Una vez clonados ambos submódulos, en los directiorios 'ChallengeJS_Alkemy\FrontEnd\my-app' y 'ChallengeJS_Alkemy\BackEnd' se deberan ejecutar los comandos:

1- npm install  (para instalar node modules)

2- npm start 

En caso de recibir el error "cb() never called" al intentar npm install en el submodulo FrontEnd, me sirvió volver a instalar npm globalmente y volver a intentar:

1- npm install -g npm

2- npm install
