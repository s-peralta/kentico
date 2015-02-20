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
Conditional Statment
--------
If culture aka lang = English do this : do this
```
<%# CultureHelper.GetPreferredCulture() == "en-CA" ? FormatDateTime(Eval("EndDate"), "MMM dd, yyyy") : FormatDateTime(Eval("EndDate"), "dd MMM, yyyy") %>

```
Transformations
--------
Images Paths with Alt
```
<img src="<%# GetAbsoluteUrl(Eval("MainImage").ToString()) %>" alt="<%# Eval("AlternativeText") %>
```
Link from list to Detail
```
<a href="<%# GetDocumentUrl() %>">Listing Anchor</a>
```
Text
```
<%# Eval("Title") %>
```
Format Date
```
<%# FormatDateTime(Eval("Date"), " MMMM dd yyyy ") %> //February 11 2015 
```

Localizatioh within a tranformation
```
 <%# ResHelper.GetString("CWP.AgeGroup") %>
```

Localization - UI Culture
--------
```
{$CODENAME$}
```

Hierarchical Accordion
--------
1 Folder Structure

- Folder <br>
  |- Question Folder <br>
     |- Answer Page w/ fields <br>
     |- Answer Page w/ fields <br>
  |- Question Folder <br>
     |- Answer Page w/ fields <br>
     |- Answer Page w/ fields <br>

2.	Adding Transformations (Use the "Hierarchical Viewer" webpart!)
```
- Main transformation (Hierarchicial)
- Header Trans. (Level 0 / Apply to Subllevels = NO / Markup = <div data-title="main-header"> )
- Header Trans (Level 1 / Apply to Subllevels = Yes / Markup = <div title="header" class="answer"> )
- Separator Trans.  (Level 0 / Apply to Subllevels = No / Markup = <div data-title="seperator"> )
- Footer Trans (Level 1 / Apply to Subllevels = Yes / Markup = “</div> </div>” )
```


Add Language Culture String
--------

- To create a culture string go to - Localization > Click "New String"
- Name your key "Project.Culture.String"
- Populate the countries with the correct content
- Go back to your page and choose either StaticText or StaticHtml as a webpart
- Within the webpart add {$KEYNAME$} Ex {$Project.Culture.String$}
-

