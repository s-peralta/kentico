Beginners Guide to Kentico
=============================

This Guide will primarily be based off of Kentico 8
<br>
<br>
Kentico Documentation Guide (https://docs.kentico.com/display/K8/Kentico+8+Documentation+Home)

Clear Cache or Restart Application
--------- 
<p>Systems > Clear Cache</p>
<p>Systems > Restart Application</p>

Common Webparts
--------- 
- __statichtml__ (Insert HTML Markup within this webpart)
- __pageplaceholder__ (For masterpage - Child's page content go within this webpart)



Create a zone
--------

```
<cms:CMSWebPartZone ZoneID="zoneTitle" runat="server" />
```


Add Language Culture String
--------

- To create a culture string go to - Localization > Click "New String"
- Name your key "Project.Culture.String"
- Populate the countries with the correct content
- Go back to your page and choose either StaticText or StaticHtml as a webpart
- Within the webpart add {$KEYNAME$} Ex {$Project.Culture.String$}
