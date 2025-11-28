I'm an engineer working on a project to takeover a large enterprises Active Directory group policy infrastructure. They have over 500 GPO's and the GPMC editor is slow as heck.
My goal is to create a single page web app that can show essentially the same thing as the GPMC editor but operate much faster. I will be provided exports of the Organization Units, WMI Filters, Group Policy Objects, and Group Policy Reports.  I need the single page webapp to initially display a breif welcome message to the Contoso user and provide 3 javascript upload forms, 
1. for the OU Json
2. for the GPO Json
3. for the Wmi Json

Once uploaded, I need the webpage to render an OU heirarchy layout of the based on the ParentOUs layed out in an IndentedTreeViewer.  The OU's should be expandable and collapsable via a Green/Red +/- button to the left of the OU Name.  If an OU doesn't have child OU's but does have GPO's linked - the OU should be expandable to reveal the attached GPOs.  In line with the OU name it should list the number of GPO's linked to that OU.  GPO's with a WMI Filter should be shown in Italic font to distinguish them from GPO's without a WMI Filter.

When the Organizational unit is expanded, I want the to see the "DisplayName" of the LinkedGPO based on GP.json matched entity for "Id"

If the matched GP entity contains a WmiFilter, grab the "msWMIName" & "msWMI-Parm2" from the wmi.json file and include that in a slighly smaller font below the GPO Name.

Attached are sample data of the 3 json files that the user will upload.  Please ensure that the webpage works based on them..  

{produced a non working site.}
Something isn't right, the Parent OU of Administration is "DC=Contoso,DC=com" and Tier 0 is a child of Administration.  That isn't reflected in the result of your response. 
Additionally, the GPO count, name, and WMI filter is missing from the table.

For matched geo's please lookup the guid from LinkedGPO in OU.json and matching it to the ID of the GP.json file.

For matched WMI Filters, please lookup the guid "WmiFilter" in the gp.json and looking up in the wmi.json