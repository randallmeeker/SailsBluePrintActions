SailsBluePrintActions
=====================

Custom blueprint action that:

##Attach 'where' query params
Uses req.options.where to limit criteria on all actions. Default sails.js blueprint actions only do this on the find action. This is usefull if you want to limit your record set so that the user can see by adding criteria to the req.options.where in a policy. Example, a user should only see the records he / she creates themselves. By adding {userId : 1} to the req.options.where in a policy, we have now limited their access. 

##Add Pagination info to the find action
Basically it will return the following
```
{
 info: {
  start: 40
  end: 70
  total: 198
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

