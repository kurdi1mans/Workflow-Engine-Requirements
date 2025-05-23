Tags:: [[Tag]]
_________________

```dataview
table without id
file.link as File,
join(Tags, ", ") as Tags
from "" 
where contains(file.outlinks, this.file.link)
```
