# homework1

## Table of Contents

## Objective

A sed command which does following:

1. Takes a backup of the existing file with the current date as it's extension .YYYY-MM-DD.
2. Case-insensitively replaces all occurrences of abc at the beginning of a line only with xyz for NFS mounts only.

## Command Description

sed -E -c -i.$(date "+%Y-%m-%d") '/([^ ]* ){2}nfs/ s/^(abc)+/xyz/i' /root/fstab

* -E Extended type Regular Expression.
* -c Copy the file when taking backup.
* -i.$(date "+%Y-%m-%d") Create the backup file with current day in required format as extension.
* '/([^ ]* ){2}nfs/ s/^(abc)+/xyz/i' - The regular expression matches lines having "nfs" in third column. Columns are separated by space. If matched line begins with "abc" (one or more occurences), then it's replaced with "xyz".
* /etc/fstab - the file.

## Reference



