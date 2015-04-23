These make changes to find.js to return pagination info.

##RangeHeader
This will accept and insert a range header with with pagination info
```
Request Header - Range : 20-30
Response Header - Range : 20-30/100
or
Request Header - X-Range : 20-30
Response Header - X-Range : 20-30/100
```

##inBody
This will return pagination info in the body
**api.com/events?companyId=1&skip=40&limit=30** will return the following
```
{
 info: {
  start: 40
  end: 70
  total: 198
  limit: 30
  criteria: {
   companyId: 1
  }
 }
 items: [
  {
   company: 1
   id: 41
   name: "Franks Condos"
  }
  {
   company: 1
   id: 42
   name: "Bobs Filmfest"
  }
  {...}
 ]
} 
```
