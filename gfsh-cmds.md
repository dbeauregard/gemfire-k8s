# Sample GFSH Commands and Example
> [!IMPORTANT]
> Run these commands in GFSH after connecting. `gfsh> `

1. Create a partitioned region
```shell
create region --name=myRegionPart --type=PARTITION_REDUNDANT
```
2. Create a replicated region
```shell
create region --name=myRegionRep --type=REPLICATE
```
3. List the regions
```shell
list regions --verbose
```
4. Add entries to the regions
```shell
put --region=/myRegionPart --key=1 --value="value1"
put --region=/myRegionRep --key=1 --value="value1"
```
5. Add more entries; as many as you like (change the key and value)
6. List the regions again and see the entry count
```shell
list regions --verbose
```
7. Retreive an entry
```shell
get --region=/myRegionPart --key=1
```
7. Update an entry and read it back
```shell
put --region=/myRegionPart --key=1 --value="NEWvalue1"
get --region=/myRegionPart --key=1
```
8. Run an OQL Query
```shell
query --query="select * from /myRegionPart limit 10"
```
8. Delete an entry and try and get it
```shell
remove --region=/myRegionPart --key=1
get --region=/myRegionPart --key=1
```