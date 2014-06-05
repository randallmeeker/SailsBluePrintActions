SailsBluePrintActions
=====================

To install, place the files in the /blueprints folder in your api/blueprints folder

What is this? Custom blueprint actions that:

##Attach 'where' query params
Uses req.options.where to limit criteria on all actions. Default sails.js blueprint actions only do this on the find action. This is usefull if you want to limit your record sets after checking access in a policy. Example, a user should only see the records he / she creates themselves. By adding {userId : req.session.user.id} to the req.options.where object in a policy, we have now limited their access provided all the records being accessed have a userId field to filter on.

##Add Pagination info to the find action
**api.com/events?companyId=1** will return the following
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

