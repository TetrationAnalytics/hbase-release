Steps to build release tar.gz:

1) mvn versions:set -DnewVersion=0.99.1234 ( Set to a version which we want to use)
2) mvn clean package -DskipTests assembly:single -Dassembly.file="hbase-assembly/src/main/assembly/src.xml" -Prelease
3) Copy the tar.gz as -src.tar.gz
4) mvn clean install -DskipTests assembly:single -Prelease
5) Copy the tar.gz as -bin.tar.gz
6) Run a binary server on the directory with the 2 tar.gz in apache archive dir structure, like hbase/hbase-version/..tar.gz
