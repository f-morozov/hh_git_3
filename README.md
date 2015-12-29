git init

vim task3.txt

git hash-object -w task3.txt

#e5791419fa06dbc7637fd229a040a1f7e058e734

git update-index --add --cacheinfo 100644 e5791419fa06dbc7637fd229a040a1f7e058e734 task3.txt

git write-tree

#6940c551a745ccfc8602a87ecf48a7d0e514a01a

echo "commit f-morozov 1" | git commit-tree 6940c5

#d176e20ff0484c9631afd8824b06e2d3b88f500c

vim task3_new.txt

git hash-object -w task3_new.txt

#8a229cbf1e21f41997e918fc7d994b598aa3b787

git update-index --add --cacheinfo 100644 8a229cbf1e21f41997e918fc7d994b598aa3b787 task3_new.txt

vim task3.txt

git hash-object -w task3.txt

#f829e5eaff06415da885add2406284e76d9671b1

git update-index --add --cacheinfo 100644 f829e5eaff06415da885add2406284e76d9671b1 task3.txt

git write-tree

#49ddb902e72151dc077126cd33b49178e5895e6d

echo "commit f-morozov 2" | git commit-tree 49ddb9 -p d176e2

#77e18c35c2086b390cc29b3891e4698dec3a2520

git read-tree --prefix=gittask 6940c551a745ccfc8602a87ecf48a7d0e514a01a

git write-tree

#b4d5ef52f4e9644d161f37c1730d0d3e1da25cda

echo "commit f-morozov 3" | git commit-tree b4d5ef -p 77e18c

#9755e48946ba131d5f3d903e32e41c9ffd82c4bc

echo "9755e48946ba131d5f3d903e32e41c9ffd82c4bc" > .git/refs/heads/master