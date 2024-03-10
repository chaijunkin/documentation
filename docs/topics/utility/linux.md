```bash
#! /bin/bash
# get the total internet usage for a particular day

totalUsage=0

for file in $1/* # $1 represents directory of Netstat keyed in by user
do
	for logf in $file/*.log
	do
		let totalUsage+=$(gawk 'BEGIN{FS=";"} {sum+=$4} END{print sum}' $logf)
	done 
done

# Show the total usage
echo -e "Total usage = $totalUsage KB"
```