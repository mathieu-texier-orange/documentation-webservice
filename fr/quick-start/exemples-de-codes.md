---
title: exemples-de-codes
description: 
published: true
date: 2024-10-31T14:45:29.845Z
tags: 
editor: markdown
dateCreated: 2024-10-24T13:15:45.199Z
---

# Exemples de codes

### Quick Start

Une connexion via Python est nécessaire pour visualiser cet exemple :

```python
#!/usr/bin/python
#-- coding:Utf-8 --import sys
import requests
import jsonsrv = "v3.oceansystem.com"
prt = 443
token = None;def send_recv_post(req,met):
   r = requests.post("https://" + srv + ":" + str(prt) + "/ocean-3.0.0/restapi/" + met + req)
   print r.text
   print r.content
   print r.json
   print r.status_code
   return rdef getToken():
   # preparation de la requete auth
   oceanuser = "XXXXXXX"
   oceanpass = "XXXXXXX"
   token = None   dataToSend = "?login=" + oceanuser + "&password=" + oceanpass   r = send_recv_post(dataToSend,"auth/authenticate")
   if int(r.status_code)==200:
       dataJson = json.loads(r.content)
       print dataJson['token']
       token = dataJson['token']
       return True
   else:
       token = None
       return Falseif getToken() :
  print "Connected"
```