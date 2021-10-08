# SharePoint Site Scripts

## How to use

1. Upload site script to SPO using M365 CLI or Powershell PnP

    Using M365 CLI:

    `m365 spo sitescript add -t {new site script title} -d {new site script description} -c {your JSON site script}`
    
    There seem to be issues trying to read the JSON directly in the command line. After '-c ' add single quotations and paste
    your entire JSON script, then close the quotation.

2. Create site design and add created site script ID to design

    Using M365 CLI:
    
    `m365 spo sitescript get`

    Note down the GUID of your site script (and any others you may want to include).

    `m365 spo sitedesign add -t { new site design title } -w { TeamSite or CommunicationSite } -d { new site design description } -s { comma separated list of script GUIDs }`

3. Create new site in SharePoint and you should be able to select your new Template aka Site Design.