SCA LAB  (pembuktian keakuratan sca MAVEN)

link :
https://www.petanikode.com/java-maven/
Stage 1 add package to pom and build
Stage 2 staging,commit and push to repo
Stage 3 scan sca 1
Stage 4 fixing and build (change pom gson to v 2.12.1)
Stage 5 staging,commit and push to repo
Stage 6 scan sca 2
gson version list : 
https://mvnrepository.com/artifact/com.google.code.gson/gson
gson ass direct dependency before fixing , and after fixing 2.12.1 have transitive dependency error prone . to check "mvn dependency:tree"
dan dari tools SCA menganggap error prone sebagai direct dependency bukan transitive , maka dipastikan manual dari "mvn dependency:tree" atau cek smua package yg dipakai tnpa ada pemebda direct/transitive"mvn dependency:list"
kesimpulannya banyak yg direct dependency dianggap ssi sca tools, namun di pom xml tidak akan didefine (tidak ada) sama spt transitive karena memang tdk didefine
karena aslinya transitive namun kelemahannya dri tools scanning tdk ketahuan induknya, melainkan harus cek tree, dan cek jika direct menggunakan list sudah pasti jadi direct di scanning tools
tree
 
