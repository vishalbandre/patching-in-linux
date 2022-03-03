vish@ubuntu:~/dev/learn-git/patching/examples$ mkdir 1
vish@ubuntu:~/dev/learn-git/patching/examples$ cd 1
vish@ubuntu:~/dev/learn-git/patching/examples/1$ touch index.html
vish@ubuntu:~/dev/learn-git/patching/examples/1$ code index.html
vish@ubuntu:~/dev/learn-git/patching/examples/1$ code .
vish@ubuntu:~/dev/learn-git/patching/examples/1$ diff -u index.html index2.html
--- index.html	2022-03-03 08:51:02.105121259 +0530
+++ index2.html	2022-03-03 08:51:13.142625893 +0530
@@ -1,7 +1,15 @@
-<html>
+<!DOCTYPE html>
+<html lang="en">
 
 <head>
-    <title>Welcome</title>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
 </head>
 
+<body>
+
+</body>
+
 </html>
\ No newline at end of file
vish@ubuntu:~/dev/learn-git/patching/examples/1$ diff -u index.html index2.html > changes.patch
vish@ubuntu:~/dev/learn-git/patching/examples/1$ ls
changes.patch  index2.html  index.html
vish@ubuntu:~/dev/learn-git/patching/examples/1$ cat changes.patch
--- index.html	2022-03-03 08:51:02.105121259 +0530
+++ index2.html	2022-03-03 08:51:13.142625893 +0530
@@ -1,7 +1,15 @@
-<html>
+<!DOCTYPE html>
+<html lang="en">
 
 <head>
-    <title>Welcome</title>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
 </head>
 
+<body>
+
+</body>
+
 </html>
\ No newline at end of file
vish@ubuntu:~/dev/learn-git/patching/examples/1$ patch < changes.patch
patching file index.html
vish@ubuntu:~/dev/learn-git/patching/examples/1$ cat index.html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>

</body>

</html>vish@ubuntu:~/dev/learn-git/patching/examples/1$ 

