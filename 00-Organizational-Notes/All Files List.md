Tags:: [[Organizational-Notes]]
Order:: 1
_________________
## Organizational Notes
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
where contains(Tags, [[Organizational-Notes]])
sort Order
```

## Domain Analysis
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
where contains(tags, [[Domain-Analysis]])
sort Order
```

## Un-Categorized
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
where contains(Tags, [[Un-Categorized]])
sort Order
```

## Cybersecurity, Authentication, and Access-Control
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
where contains(Tags, [[Cybersecurity]]) or contains(Tags,[[Access-Control]])
sort Order
```

## Others Requirements
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
where 
contains(Tags, [[Requirements]])
and !(contains(Tags, [[Cybersecurity]]) or contains(Tags,[[Access-Control]]))
and !contains(Tages, [[Un-Categorized]])
sort Order
```


## All files
```dataview
table without id
Order,
file.link as "File",
join(Tags, ", ") as Tags
from ""
sort Order
```
